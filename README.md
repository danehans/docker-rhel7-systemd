docker-rhel7-systemd
====================

Docker Image for RHEL7 with Systemd

Introduction
------------

This guide assumes you have Docker installed on your host system. Use the [Get Started with Docker Containers in RHEL 7](https://access.redhat.com/articles/881893] to install Docker on RHEL 7) to setup your Docker on your RHEL 7 host if needed.

Reference the [Getting images from outside Docker registries](https://access.redhat.com/articles/881893#images) section of the [Get Started with Docker Containers in RHEL 7](https://access.redhat.com/articles/881893) guide
to pull your base rhel7 image from Red Hat's private registry. This is required to build the rhel7-systemd image.

Next, verify your Docker Registry is running:
```
# systemctl status docker-registrydocker-registry.service - Registry server for Docker
   Loaded: loaded (/usr/lib/systemd/system/docker-registry.service; enabled)
   Active: active (running) since Mon 2014-05-05 13:42:56 EDT; 601ms ago Main PID: 21031 (gunicorn)
   CGroup: /system.slice/docker-registry.service
           ├─21031 /usr/bin/python /usr/bin/gunicorn --access-logfile - --debug ...            ...
```
Now that you have the rhel7 base image, clone the docker-rhel7-systemd project and build your rhel7-systemd image:
```
# yum install -y git
# git clone https://github.com/danehans/docker-rhel7-systemd.git \
 $HOME/docker-rhel7-systemd && cd $HOME/docker-rhel7-systemd
# docker build -t ouruser/rhel7-systemd .
```
**Note:** The rhel7-systemd image was prepended with username, ouruser, that we're writing this image to.
Replace ouruser with your own unique username. For more details reference the [Working with Docker Images](https://docs.docker.com/userguide/dockerimages/) user guide.
