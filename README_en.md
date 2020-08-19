Remove all unused or dangling resources
OBS: a dangling resource is a image, container, volume, and network that is not associated with a container.
docker system prune [-a]
[-a] Remove all of the above plus stopped containers and all unused images

List all docker images with their associated IDs
docker images -a

Remove image
docker rmi [-f] image
[-f] Force removal

Remove dangling images
OBS: a dangling image is a layer that is not associated with any tagged image. Located them with the filter option [-f dangling=true]
docker images -f dangling=true
docker image prune

List all images that match a pattern
- Linux
List: docker images -a |  grep "pattern"
- Windows (CMD)
docker images -a |  findstr "pattern"
- Windows (PowerShell)
docker images -a |  Select-String "pattern"

Remove all images that match a pattern
- Linux
docker images -a | grep "pattern" | awk '{print $3}' | xargs docker rmi

Remove all images
docker rmi $(docker images -aq)
[-q] Shows only image ID (in this special case, all image IDs will be passed to docker rmi)

docker build
docker image ls [-a]
docker image rm [-f]
docker container ls [-a]
docker container rm [-f]
docker container exec [-it]
docker container run
docker ps [-a]
docker login
docker tag
docker tag local-image:tagname new-repo:tagname
docker push new-repo:tagname

verificar resumo do consumo do docker: tamanho total de imagens, containers, volume local, e cache
docker system df

verificar tamanho de cada container em execução
docker ps --size

verificar tamanho de todos os containers
docker ps -a --size

remover todas as imagens não vinculadas a containers
docker image prune -af

Links:

https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes
