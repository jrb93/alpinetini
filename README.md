# Alpinetini #

[![](https://images.microbadger.com/badges/image/jrb93/alpinetini.svg)](https://microbadger.com/images/jrb93/alpinetini "Get your own image badge on microbadger.com")
`alpinetini` is a base image for running [tini](https://github.com/krallin/tini) a tiny init process with [Alpine Linux](https://www.alpinelinux.org/) on [Docker](https://www.docker.com).

## Overview ##

* Version **1.1.0**
* Combines a tiny [Alpine Linux](https://www.alpinelinux.org/) os with a [tini](https://github.com/krallin/tini) init process
* Protects from [*zombie processes* and ensures *default signal handlers* work](https://github.com/krallin/tini#why-tini)
* Download size = 2.6MB
* Total image size = 5.7MB

## Supported tags ##

* [![](https://images.microbadger.com/badges/version/jrb93/alpinetini:3.1.svg)](https://microbadger.com/images/jrb93/alpinetini:3.6 "Get your own version badge on microbadger.com") [(versions/3.1/Dockerfile)](https://github.com/jrb93/alpinetini/tree/master/versions/3.1)
* [![](https://images.microbadger.com/badges/version/jrb93/alpinetini:3.2.svg)](https://microbadger.com/images/jrb93/alpinetini:3.6 "Get your own version badge on microbadger.com") [(versions/3.2/Dockerfile)](https://github.com/jrb93/alpinetini/tree/master/versions/3.2)
* [![](https://images.microbadger.com/badges/version/jrb93/alpinetini:3.3.svg)](https://microbadger.com/images/jrb93/alpinetini:3.6 "Get your own version badge on microbadger.com") [(versions/3.3/Dockerfile)](https://github.com/jrb93/alpinetini/tree/master/versions/3.3)
* [![](https://images.microbadger.com/badges/version/jrb93/alpinetini:3.4.svg)](https://microbadger.com/images/jrb93/alpinetini:3.6 "Get your own version badge on microbadger.com") [(versions/3.4/Dockerfile)](https://github.com/jrb93/alpinetini/tree/master/versions/3.4)
* [![](https://images.microbadger.com/badges/version/jrb93/alpinetini:3.5.svg)](https://microbadger.com/images/jrb93/alpinetini:3.6 "Get your own version badge on microbadger.com") [(versions/3.5/Dockerfile)](https://github.com/jrb93/alpinetini/tree/master/versions/3.5)
* [![](https://images.microbadger.com/badges/version/jrb93/alpinetini:3.6.svg)](https://microbadger.com/images/jrb93/alpinetini:3.6 "Get your own version badge on microbadger.com"), [![](https://images.microbadger.com/badges/version/jrb93/alpinetini:latest.svg)](https://microbadger.com/images/jrb93/alpinetini:3.6 "Get your own version badge on microbadger.com") [(versions/3.6/Dockerfile)](https://github.com/jrb93/alpinetini/tree/master/versions/3.6)
* [![](https://images.microbadger.com/badges/version/jrb93/alpinetini:edge.svg)](https://microbadger.com/images/jrb93/alpinetini:3.6 "Get your own version badge on microbadger.com") [(versions/edge/Dockerfile)](https://github.com/jrb93/alpinetini/tree/master/versions/edge)

### How to use ###

To use this as a base for another Docker image simply create a new Dockerfile and enter:

```Dockerfile
FROM jrb93/alpinetini
```

Then add any commands or files you want to run. The **ENTRYPOINT** is already set to run [tini](https://github.com/krallin/tini) in this base image, so all that's needed is a [**CMD** at the end of the file](https://github.com/krallin/tini#using-tini)

```Dockerfile
CMD ["/your/program", "-and", "-its", "arguments"]
```

You can also directly run this image into the shell by running the following command:

```ShellSession
docker run -it jrb93/alpinetini /bin/sh
```

To check that tini is running as **PID 1** type `ps` into shell:

```ShellSession
/ # ps
PID   USER     TIME   COMMAND
    1 root       0:00 /tini -- /bin/sh
    5 root       0:00 /bin/sh
    6 root       0:00 ps
```