### Examples
Use a Postgres database, no admin user enabled:

```
docker run -d \
	--name etherpad         \
	-p 9001:9001            \
	-e 'DB_TYPE=postgres'   \
	-e 'DB_HOST=db.local'   \
	-e 'DB_PORT=4321'       \
	-e 'DB_NAME=etherpad'   \
	-e 'DB_USER=dbusername' \
	-e 'DB_PASS=mypassword' \
	etherpad/etherpad
```
Run enabling the administrative user admin:

```
docker run -d \
	--name etherpad \
	-p 9001:9001 \
	-e 'ADMIN_PASSWORD=supersecret' \
	etherpad/etherpad
```

Run a test instance running DirtyDB on a persistent volume:

```
docker run -d \
	-v etherpad_data:/opt/etherpad-lite/var \
	-p 9001:9001 \
	etherpad/etherpad
```