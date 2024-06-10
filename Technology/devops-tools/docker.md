# Docker

## Overview

Docker is a tool used to package a software application along with all of its dependencies in an isolated environment called a `container`. Containers can run reliably on any machine regardless of the operating system or underlying hardware. They are stateless (changes and data are lost after constainer is stopped) and therefore portable (can run on any cloud provider)

Unlike a virtual machine, which has it's own full OS, Docker containers use the host OS and are all run on the same engine/kernel. This makes them much faster and more lightweight. Also, a VM's allocation of resources (CPU and memory) are fixed whereas a Docker container can dynamically allocate resources. based on an applications needs.

A `Dockerfile` is the code that is executed to build an image. It is used to configure the environment for your application.

An `image` is a blueprint of the application along with its dependencies and configuration. It is a template and is used to build a `container`.

```dockerfile
FROM image-template
CMD
```

A `.dockerignore` file can specify files to not be copied into the image.

## Dockerfile Instructions

`FROM` points to a base image

`WORKDIR` creates a working directory to work in

`RUN` uses a package manager to install dependencies

`USER` creates a non-root user for better security

`COPY` moves code from your local machine over to the image

`ENV` declares environment variables

`CMD` starts up a container

## Commands

`docker help` displays all the possible commands

`docker build` builds an image from a Dockerfile. `-t` creates a tag for the image

`docker run` runs the image as a container

`docker push` uploads image to remote registry on the cloud

`docker pull` downloads an image from the cloud

## Docker-compose
