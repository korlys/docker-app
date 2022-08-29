To use this image with MySQL, MariaDB or PostgreSQL you will need a suitable database running externally. This may be through a Docker image, possibly in your docker-compose.yml.

Create the db, username, password.
Edit the environment variables (db credentials, language...) by :
Supplying the environment variables via docker run / docker-compose or
Creating a .env file with the appropriate info and mount it to /conf/.env or
Use the Lychee installer by passing -e DB_CONNECTION= on the command line and connecting to the container with your browse