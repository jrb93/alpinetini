# Alpinetini-base #

`alpinetini-base` is a base image for running [tini](https://github.com/krallin/tini) a tiny init process with [Alpine Linux](https://www.alpinelinux.org/) on [Docker](https://www.docker.com).

## Overview ##

* Version **1.1.0**
* Combines a tiny [Alpine Linux](https://www.alpinelinux.org/) os with a [tini](https://github.com/krallin/tini) init process
* Protects from [*zombie processes* and ensures *default signal handlers* work](https://github.com/krallin/tini#why-tini)

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