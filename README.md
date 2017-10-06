# Alpinetini-base #

`alpinetini-base` is a base image for running [tini](https://github.com/krallin/tini) a tiny init process with [Alpine Linux](https://www.alpinelinux.org/) on [Docker](https://www.docker.com).

## Overview ##

* Version **1.0.0**
* Combines a tiny [Alpine Linux](https://www.alpinelinux.org/) os with a [tini](https://github.com/krallin/tini) init process
* Protects from [*zombie processes* and ensures *default signal handlers* work](https://github.com/krallin/tini#why-tini)