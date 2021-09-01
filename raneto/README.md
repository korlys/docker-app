docker cli (click here for more info)
docker run -d \
  --name=raneto \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/London \
  -p 3000:3000 \
  -v /path/to/appdata:/config \
  --restart unless-stopped \
  ghcr.io/linuxserver/raneto


Application Setup
Access the webui at http://

The default username and password is admin/password

This application can only be configured through file storage the web interface is only for editing Markdown files. You need to understand the following paths and the role they play for the application:

/config/config.default.js - Main configuration file to setup your user, site name, etc.
/config/content - All of your Markdown files go here more info.
/config/images - This folder will serve content on http://