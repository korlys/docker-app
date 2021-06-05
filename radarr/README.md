## radarr


### docker run

```
docker run -d \
  --name=radarr \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/London \
  -p 7878:7878 \
  -v /path/to/data:/config \
  -v /path/to/movies:/movies `#optional` \
  -v /path/to/downloadclient-downloads:/downloads `#optional` \
  --restart unless-stopped \
  ghcr.io/linuxserver/radarr

```