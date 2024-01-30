---
layout: post
title: Docker-pilled
date:   2024-01-31 04:20:21 +0530
categories: dev
---

After trying to learn Docker 5 times, I finally understood it enough to make sense of the whole thing.

I have made notes for learning that I'll share at the end of this post.

Learning docker has made me feel liberated. It feels like a god-send technology when working with co-workers remotely. Nothing to discuss, just share the Dockerfile and move forward, docker has all the required things to work.

I had resisted in using docker a lot, mostly because of my ignorance its powers and understanding it well. Tutorials weren't really of much help.

Release of the [Kamal](https://kamal-deploy.org/) tool and Rails including Docker with 7.1 by default finally tipped me over the edge to learn it practically.

Found a client that wanted to dockerize their app and voila, I've understood docker in 3 days and feel comfortable now!

Just want to get my hands dirty with some open source docker apps now!

## Learning Notes:

Docker helps with having us a consistent experience.

VM vs Container

Container - An isolated environment for running an application

VM - An abstraction of machine (physical hardware)

VMWare and Virtual box are called Hypervisors.

VM need a full blown OS, they're slow to start and are resource intensive.

Containers also provide us isolation, letting us run multiple apps in an isolated manner. They're lightweight compared to VMs, and use the OS of the host. They start quickly and need less hardware resources.
**They use the kernel of operating system.**

Docker has a client server arch. Client talks to server using a rest API on the machine. The server is called Docker Engine.

Instead of running the program, we ask Docker to run a program by calling `docker run ...`

##### BUILD

`docker build -t {IMAGE_NAME} {DIRECTORY}`

`docker images` or `docker image ls` shows all the images on the machine

`docker run {IMAGE_NAME}` to run the application. The directory doesn't matter as it runs the image from image registry on machine. If an image is not available locally, it is pulled from docker hub.

https://labs.play-with-docker.com/ to play around with docker on a VM


```
FROM node:alpine # use node from alpine OS

COPY . /app # copy the contents of `.` and put it in the container's /app

WORKDIR /app # run commands in /app

CMD node app.js # command to run
```

`docker ps` gives us a list of running containers. `docker ps -a` also shows stopped images.

`docker run -it {IMAGE_NAME}` is basically like an SSH into the container.

#### Arguments and ENV

To set an argument that can be provided from command line while building:

```
ARG NAME=Docker
ARG SALUTATION=Hello2
```

This is to set argument for creating image. Value set in Dockerfile is default and can set from command line. To set ARG:

```
docker build -t {image-name} . --build-arg "NAME=SHOBHIT"
```

For ENV variables, you can use 

```
ENV NAME=$NAME
ENV SALUTATION=Hello
```

Here `$NAME` come from one of the arguments (`ARG`). Value set in Dockerfile is default and can set from command line.

Run this by:

```
docker run -e "NAME=SHOBHIT SALUTATION=NAMASTE" {image-name}
```

#### Running different commands

To run default:

```
docker run {image-name}
```

To change the command:

```
docker run {image-name} node run.js
```

This runs a different file called run.js


### Docker Compose

Remove all images - 

```bash
docker image rm -f $(docker image ls -q)
```

Remove all containers - 

```bash
docker container rm -f $(docker container ls -qa)
```

Port is mentioned as `host-port:container-port`

Run

```
docker-compose up
```

to execute. and `build` to generate the container.

For a full rebuild,

```
docker-compose build --no-cache
```


