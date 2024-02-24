## Docker Commands

### Display system info
> docker info

### Display system's version
> docker version

### Login to docker registry
> docker login -u username -p password

### Pull an image from a registry
> docker pull image-name

### Push an image to registery
> docker push registery-name/image-name:tag

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

### Execute a command in a running container
> docker exec -it container-name command

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

### Build an image using a Dockerfile located in the same folder
> docker build -t name:tag .

### Build an image using a Dockerfile located in a different folder
> docker build -t name:tag -f filename

### Tag an existing image
> docker tag image-name name:tag

### Create a new volume
> docker create volume volume-name

### List volumes
> docker volume ls

### Display volume info
> docker volume inspect volume-name

### Delete a volume
> docker volume rm volume-name

### Deletes all volumes not mounted
> docker volume prune

### Run a container with volume
> docker run -d --name container-name -v volume-name:/mount-folder-name image-name:tag

### Run a container with volume (specify a local folder)
> docker run -d --name container-name -v d:/test:/mount-folder-name image-name:tag


## Docker Compose Commands

### Build the images
> docker compose build

### Start containers
> docker compose start

### Stop containers
> docker compose stop

### Build and start
> docker compose up -d

### List what's running
> docker compose ps

### Remove from memory
> docker compose rm

### Stop and remove
> docker compose down

### Get the logs
> docker compose logs

### Run a command in a container
> docker compose exec container-name command-name

### Run an instance as a project
> docker compose --project-name project-name up -d

> docker compose -p project-name up -d

### List running projects
> docker compose ls

### Copy files from container
> docler compose cp containerid:src-path dest-path

### Copy files to container
> docker compose cp src-path container-id:dest-path



