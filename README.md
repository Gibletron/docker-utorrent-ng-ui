# Docker uTorrent NG UI

This is a fork of the [Docker uTorrent](https://github.com/ekho/dockerized-tools/).
Which is the Dockerfile setup for [uTorrent](http://www.utorrent.com/).

## Why another container?

The container differs from the above by the [NG Web UI] {https://github.com/psychowood/ng-torrent-ui/), which I prefer.

## Running
You can use the following config to run the container.
You might need to adapt it to your specific config


```yml
version: '3'
services:
  utorrent:
    image: gibletron/utorrent-ng-ui:latest
    container_name: utorrent
    volumes:
      - /path/to/data/dir:/utorrent/data
      - utorrent-settings:/utorrent/settings
      - /path/to/utserver.conf:/utorrent/utserver.conf
    environment:
      HOST_UID: 1002
      HOST_GID: 1002
    ports:
      - 8080:8080
      - 6881:6881
    restart: always
    logging:
      driver: "json-file"
      options:
        max-size: "10m"
        max-file: "3"
volumes:
  utorrent-settings:
```


You can find the dockerhub page right here: https://hub.docker.com/r/gibletron/utorrent-ng-ui
