# Docker containers for usenet setup

Edit the `uidgid.env` with your users id. You can get this by running the command `id`. For example if the command gave you:

```
$ id
uid=1000(ryan) gid=1000(ryan)
```

You would update the file to be:

```
PGID=1000
PUID=1000
```

## Deploy containers

`docker-compose up -d`