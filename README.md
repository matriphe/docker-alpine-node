# Alpine Node

This Node.js docker image is based on [Alpine](https://hub.docker.com/_/alpine/). Alpine is based on [Alpine Linux](http://www.alpinelinux.org), lightweight Linux distribution based on [BusyBox](https://hub.docker.com/_/busybox/). The size of the image is very small, less than 50 MB!

## Tags

Versions and are based on Node.js versions.

Here are the supported tags and respective Dockerfile links.

 * `node-0.12.2`, `npm-3.5.0`, `latest` [(Dockerfile)](https://github.com/matriphe/docker-alpine-node/blob/master/Dockerfile)
 
## Getting The Image

This image is published in the Docker Hub. Simply run this command below to get it to your machine.

```Shell
docker pull  matriphe/alpine-node:latest
```

Alternatively you can clone this repository and build the image using the `docker build` command.

## Build

This image use `Asia/Jakarta` timezone by default. You can change the timezone by change the `TIMEZONE` environment on `Dockerfile` and then build.

```Shell
docker -t repository/imagename:tag Dockerfile
```
## Run The Container

### Create and Run The Container

```Shell
docker run  matriphe/alpine-node:latest
```

By default, it will run the `node` command. You can pass the Node or NPM command to this container. Here's the example.

```Shell
docker run  matriphe/alpine-node:latest docker node --version
```

```Shell
docker run  matriphe/alpine-node:latest npm --version
```

### Create an alias

Add to your `~/.bashrc` this line, so you can just type `node` or `npm` command from command line. Make sure the docker engine is running.

```Shell
alias node='docker run --rm --name=node -v $(pwd):/www  matriphe/alpine-node:latest node'
alias npm='docker run --rm --name=npm -v $(pwd):/www  matriphe/alpine-node:latest npm'
```

And then execute this command to make alias working.

```Shell
source ~/.bashrc
```

Now you can just simply type `composer` from command line.