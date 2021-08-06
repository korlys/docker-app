Parameters
The parameters are split into two halves, separated by a colon, the left hand side representing the host and the right the container side.

--net=host - Shares host networking with container, required
-v /homebridge - The Homebridge config and plugin location
Optional Settings:
-e PGID - for group id - see below for explanation
-e PUID - for user id - see below for explanation
-e TZ - for timezone information e.g. -e TZ=Canberra/Australia
Homebridge UI Options:
-e HOMEBRIDGE_CONFIG_UI=1 - Set to 0 to disable the Homebridge UI.
-e HOMEBRIDGE_CONFIG_UI_PORT=8581 - The port to run the Homebridge UI on. Defaults to port 8581.
User / Group Identifiers
Sometimes when using data volumes (-v flags) permissions issues can arise between the host OS and the container. We avoid this issue by allowing you to specify the user PUID and group PGID. Ensure the data volume directory on the host is owned by the same user you specify and it will "just work".

In this instance PUID=1001 and PGID=1001. To find yours use id user as below:

  $ id <dockeruser>
    uid=1001(dockeruser) gid=1001(dockergroup) groups=1001(dockergroup)
Homebridge UI
This image comes with the Homebridge UI pre-installed and is the easiest way to manage all aspects of Homebridge.

To manage Homebridge go to http://<ip of server>:8581 in your browser. For example, http://192.168.1.20:8581. From here you can install, remove and update plugins, modify the Homebridge config.json and restart Homebridge.

The default username is admin and the default password is admin.