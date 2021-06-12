### Application Setup
The webui is at <your ip>:8200 , create backup jobs etc via the webui, for local backups select /backups as the destination. For more information see Duplicati.


### Environment variables from files (Docker secrets)
You can set any environment variable from a file by using a special prepend FILE__.

As an example:

-e FILE__PASSWORD=/run/secrets/mysecretpassword
Will set the environment variable PASSWORD based on the contents of the /run/secrets/mysecretpassword file.