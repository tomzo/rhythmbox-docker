# Rhythmbox in docker

Rhythmbox installed on ubuntu phusion base image.

There are several approaches to running GUI apps in docker. My favorite
is to run X server on docker host and use unix sockets in docker volume.

Sound should be fine as long as it was already installed on host.

You may need to install graphics drivers inside the container.
They should be exactly the same as in host.

# Usage

```
docker run -e DISPLAY=unix:0.0 --privileged -ti -v /tmp/.X11-unix:/tmp/.X11-unix -v /music:/music tomzo/rhythmbox
```
