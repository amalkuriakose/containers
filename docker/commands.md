### Display system info
> docker info

### Display system's version
> docker version

### Login to docker registry
> docker login

### Pull an image from a registry
> docker pull image-name

### Run containers
> docker run image-name

### Run containers in detached mode
> docker run -d image-name

### Start stopped containers
> docker start container-name

### List running containers
> docker ps

### List running and stopped containers
> docker ps -a

### Stop containers
> docker stop container-name

### Kill containers
> docker kill container-name

### Get image info
> docker image inspect image-name

### Max memory
> docker run --memory="256m" image-name

### Max CPU
> docker run --cpus=".5" image-name

### Pull and run an image
> docker run --publish host-port:container-port --name container-name image-name

> Ex:- docker run --publish 80:80 --name webserver nginx

### Attach shell
> docker run -it image-name -- /bin/bash

### Attach shell to a running container
> docker container exec -it container-name -- bash

### Remove stopped containers
> docker rm container-name

### Remove all stopped containers
> docker rm $(docker ps -a  -q)

### List images
> docker images

### Delete image
> docker rmi image-name

### Remove all images not in use by any containers
> docker system prune -a