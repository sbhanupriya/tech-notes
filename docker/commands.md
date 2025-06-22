# Docker

_docker --version_
- check if docker is installed or not

_docker pull redis_
- downloads the docker image to your system
- by default it pulls the latest version
- If we want to specify redis:6.2.7

_docker images_
- check which all images are present in your system
- returns below columns
- Repository | Tag |  Image_Id | Created | Size

_docker run --name redis-latest -p6379:6379  -d redis:latest_

- create docker container from docker image with container name (redis-latest)
- and repository:tag to select image or we can also use image_id
- docker run --name redis-latest 1b835e5a8d5d
- -p6379 refers to host machine port 
- :6379 refers to docker container port
- -d stands for detached mode so that container runs in background, doesn't block terminal

_docker ps_

- gives list of running containers
- Container Id | Image |  Command |  Created |  Status | Ports |  Names
- If we want to see all containers(even stopped), then use _docker ps -a_

_docker stop redis-latest_

- stops the container with name redis-latest or we can give container_id

_docker start redis-latest_

- starts the container with name redis-latest or we can give container_id

_docker rm redis-latest_

- deletes the container with name redis-latest or we can give container_id


**Use Case**
Lets us suppose we want to run two versions of redis in our system
- docker pull redis
- docker pull redis:6.2.7
- docker run --name redis-latest -p6379:6379 -d redis:latest
- docker run --name redis-old -p6378:6379 -d redis:6.2.7
Here, host machine port is changed to another port, while both container have redis running on 6379


_docker inspect container_id/docker_image_

- It returns all information about image or container
- Useful in creating bash scripts

_docker logs container-id_

- Get all logs of container

_docker exec -it container_id /bin/sh_

- useful when we want to debug and run commands in container


_docker rmi image_name:tag_

- removes docker image from system

_docker system prune -a_

- It deleted unused images and stopped containers from the system


