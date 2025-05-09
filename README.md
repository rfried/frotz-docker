# Overview

This is a Dockerized frotz interpreter for Infocom and other Z-Machine games.

This is built directly from the [source repo](HERE) maintained by David Griffith. This version of frotz is built without sound in order to compile and run properly in an Alpine Linux container.

You can also visit the [Docker Hub repo](https://hub.docker.com/r/newtmitch/frotz).

# Running

```
# create a container in interactive mode, mapping your local zfiles directory into the container. Change /home/frotz
# to anything that works for you to access the zfiles
docker run -ti -v $PWD/zfiles:/home/frotz newtmitch/frotz

# start a zfile
frotz telling.z5
```

# Building

Linux
```
GIT_CHECKOUT=2.55 && \
    docker build -t rfriedgh/frotz --build-arg GIT_CHECKOUT . && \
    docker tag rfriedgh/frotz rfriedgh/frotz:$GIT_CHECKOUT
```

Windows
```
set GIT_CHECKOUT=2.55 && docker build -t rfriedgh/frotz --build-arg GIT_CHECKOUT . && docker tag rfriedgh/frotz rfriedgh/frotz:%GIT_CHECKOUT%
```

# Change Log

## 2020-11-26
* Moved to alpine linux from ubutnu
* Building directly from source and latest mainstream release tag (instead of sourceforge binary)
* staged build for smaller final image
* Added README so people can actually use this image

## 2016 (sometime)
* Initial release
