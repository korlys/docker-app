Persistent data
All data beyond what lives in the database (file uploads, etc) is stored within the default volume /var/www/html. With this volume, ownCloud will only be updated when the file version.php is not present.

-v /<mydatalocation>:/var/www/html
For fine grained data persistence, you can use 3 volumes, as shown below.

-v /<mydatalocation>/apps:/var/www/html/apps installed / modified apps
-v /<mydatalocation>/config:/var/www/html/config local configuration
-v /<mydatalocation>/data:/var/www/html/data the actual data of your ownCloud


Run docker stack deploy -c stack.yml owncloud (or docker-compose -f stack.yml up), wait for it to initialize completely, and visit http://swarm-ip:8080/, http://localhost:8080/, or http://host-ip:8080 (as appropriate).