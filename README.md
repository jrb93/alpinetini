# Alpinetini-base #

[![](https://images.microbadger.com/badges/image/jrb93/alpinetini-base.svg)](https://microbadger.com/images/jrb93/alpinetini-base "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/jrb93/alpinetini-base:3.6.svg)](https://microbadger.com/images/jrb93/alpinetini-base:3.6 "Get your own version badge on microbadger.com")
`alpinetini-base` is a base image for running [tini](https://github.com/krallin/tini) a tiny init process with [Alpine Linux](https://www.alpinelinux.org/) on [Docker](https://www.docker.com).

## Overview ##

* Version **1.1.0**
* Combines a tiny [Alpine Linux](https://www.alpinelinux.org/) os with a [tini](https://github.com/krallin/tini) init process
* Protects from [*zombie processes* and ensures *default signal handlers* work](https://github.com/krallin/tini#why-tini)
* Download size = 2.6MB
* Total image size = 5.7MB

## Supported tags ##

* 3.1 [(versions/3.1/Dockerfile)](https://github.com/jrb93/alpinetini-base/tree/master/versions/3.1)
* 3.2 [(versions/3.1/Dockerfile)](https://github.com/jrb93/alpinetini-base/tree/master/versions/3.2)
* 3.3 [(versions/3.1/Dockerfile)](https://github.com/jrb93/alpinetini-base/tree/master/versions/3.3)
* 3.4 [(versions/3.1/Dockerfile)](https://github.com/jrb93/alpinetini-base/tree/master/versions/3.4)
* 3.5 [(versions/3.1/Dockerfile)](https://github.com/jrb93/alpinetini-base/tree/master/versions/3.5)
* 3.6, latest [(versions/3.1/Dockerfile)](https://github.com/jrb93/alpinetini-base/tree/master/versions/3.6)
* edge [(versions/3.1/Dockerfile)](https://github.com/jrb93/alpinetini-base/tree/master/versions/edge)

### How to use ###

To use this as a base for another Docker image simply create a new Dockerfile and enter:
```
FROM jrb93/alpinetini-base
```
Then add any commands or files you want to run. The **ENTRYPOINT** is already set to run [tini](https://github.com/krallin/tini) in this base image, so all that's needed is a [**CMD** at the end of the file](https://github.com/krallin/tini#using-tini)
```
CMD ["/your/program", "-and", "-its", "arguments"]
```
You can also directly run this image into the shell by running the following command:
```
docker run -it jrb93/alpinetini-base /bin/sh
```
To check that tini is running as **PID 1** type `ps` into shell:
```
/ # ps
PID   USER     TIME   COMMAND
    1 root       0:00 /tini -- /bin/sh
    5 root       0:00 /bin/sh
    6 root       0:00 ps
```