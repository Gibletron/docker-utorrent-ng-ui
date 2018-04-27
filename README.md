# Docker uTorrent NG UI

This is a fork of the [Docker uTorrent](https://github.com/ekho/dockerized-tools/).
Which is the Dockerfile setup for [uTorrent](http://www.utorrent.com/).

## Why another container?

The container differs from the above by the [NG Web UI] {https://github.com/psychowood/ng-torrent-ui/), which I prefer.

## Running
You can use the following config to run the container.
You might need to adapt it to your specific config


```yml
web:
  build: .
  container_name: plex_email
  ports:
    - "8383:80"
  expose:
    - "8383"
    - "80"
  restart: always
  volumes:
    - /opt/data/plexemail:/config
    - /opt/data/plex/config:/plex
```

With the  AUTOJOIN variable, this script will ensure, your local clients never see the server selection, and instead will be connected to your local SyncLounge server every time. 
Only works, if SYNCLOUNGE_DOMAIN is accessible through https.

You can find the dockerhub page right here: https://hub.docker.com/r/gibletron/synclounge-auto/
