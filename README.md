# marscontainers
Repo for my various home server containers

### Directory creation

```
mkdir -p ~/media/config/{sabnzbd,sonarr,nzbhydra,plex}
mkdir -p ~/media/Downloads/{complete,incomplete}
mkdir -p ~/media/transcode
mkdir -p ~/media/TV
mkdir -p ~/media/Movies
mkdir -p ~/media/KidsMovies
mkdir -p ~/media/KidsTV
```

### Plex container creation 

Grab your Plex Claim token from http://plex.tv/claim/

```
docker run -d \
--restart always \
--name plex \
-p 32400:32400/tcp \
-p 3005:3005/tcp \
-p 8324:8324/tcp \
-p 32469:32469/tcp \
-p 1900:1900/udp \
-p 32410:32410/udp \
-p 32412:32412/udp \
-p 32413:32413/udp \
-p 32414:32414/udp \
-e TZ="America/Chicago" \
-e PLEX_CLAIM="CLAIM_TOKEN" \
-e ADVERTISE_IP="http://HOME_SERVER_IP:32400/" \
-v ~/media/config/plex:/config \
-v ~/media/transcode:/transcode \
-v ~/media/TV:/data/tvshows \
-v ~/media/Movies:/data/movies \
-v ~/media/KidsMovies:/data/kidsmovies \
-v ~/media/KidsTV:/data/kidstvshows \
plexinc/pms-docker
```
