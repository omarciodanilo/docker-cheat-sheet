# Docker Cheat-Sheet
### Some useful Docker commands I've used in my studies

## Summary
### [0. Used flags]
### [1. General commands]
### [2. Container commands]
### [3. Image commands]
### [4. Commands that need to be reviewd and added]
### [5. Useful links]

#

## 0. Used flags

[-a] All running, stopped, and unused containers or images

[-f] Force related action

[-q] Shows only container ID or image ID

## 1. General commands

### - Verify Docker brief resource utilization: total space used by images, containers, local volume, and cache
`docker system df`

### - Remove all unused or dangling resources
_OBS: a dangling resource is a image, container, volume, and network that is not associated with a container._

`docker system prune [-a]`

## 2. Container commands

### - List containers

`docker container ls [-a]`

### - Remove containers

`docker container rm [-f] [container-id or container-name]`

### - Verify size of each running container

`docker ps --size`

### - Verify size of all containers

`docker ps -a --size`

## 3. Image commands

### - List all docker images with their associated IDs

`docker images -a`

### - Remove image

`docker rmi [-f] [image-id or image-name]`

### - Remove dangling images
_OBS: a dangling image is a layer that is not associated with any tagged image. Located them with the filter option [-f dangling=true]_

`docker images -f dangling=true`

`docker image prune`

### - List all images that match a pattern
- Linux

`docker images -a |  grep "pattern"`

- Windows (CMD)

`docker images -a |  findstr "pattern"`

- Windows (PowerShell)

`docker images -a |  Select-String "pattern"`

### - Remove all images that match a pattern
- Linux

`docker images -a | grep "pattern" | awk '{print $3}' | xargs docker rmi`

### - Remove all images

`docker rmi $(docker images -aq)`

### - Remove all images not related to any container

`docker image prune -af`

## 4. Commands that need to be reviewd and added

`docker build`

`docker image ls [-a]`

`docker image rm [-f]`

`docker container exec [-it]`

`docker container run`

`docker container start|stop|restart`

`docker ps [-a]`

`docker login`

`docker tag`

`docker tag local-image:tagname new-repo:tagname`

`docker push new-repo:tagname`

## 5. Useful links:

[https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes]
