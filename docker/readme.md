# what is docker

from my experience on react native, there always some bug that only happen on one divce but not orther

<p align="center">
  <img  src="https://github.com/NghiaDangTran/microservice-research/assets/33323750/619051d6-8d41-4381-9746-8be17c7c0f05">
</p>

 - So what should be the solutions
   <h1>Introducing Docker</h1>
![image](https://github.com/NghiaDangTran/microservice-research/assets/33323750/da440e98-1f13-432f-bc16-32b060ee8cfc)


build anywhere and run everywhere

# Docker components:
 -  let take example where docker is a house with 4 or 5 room
 -  4 room for guest and one kitchen
in interview ask the person do you have a house or planing to use one ?
 - so suppose there are 3 people in your house, u, ur wife, and your children
 - so in the end we can summary that docker is use for mutiple application in one server or one machine
 - or to run application in mutiple enviroment
# how docker work

CLI (client machine) and docker server --> docker deamon --> check image or container and do based on that cli
</br>
layered file system--> so each new container build they have some of the same layered, so it is super memoery efficent, and they have resource isolation so taht if one container fail or take to much memoery it does not stop orther Container

everything start with a dockerfile, that is like the receipe for the docker deamon to build applications
```
FROM node:12
WORKDIR /app  # the working directory of the app
COPY pakage.json # direction for dependcy of the applications
RUN npm install  # this is a cmd to run the conamand for application
COPY . .  # copy all file to the directory
# incase u want to skip some file or process we can use .dockerignor
ENV port=8080 # env file
EXpose 8000 # a port to connect to the container
CMD ["cmd1","cmd2"]
```
RUN will Executes commands during the build phase and also make a new layered to be cached for the next time
but run with cmd will not make a new layer, like a runtime command

docker compose use a set of rule to run multiple container together

we can share data inone docker app using vloumes


# docker command
## Basic Docker Commands:

 - docker --version: Display Docker version information. 
 - docker info: Display system-wide information about Docker and its components.
## Image Commands:

 - docker images: List all images on your local system.
 - docker rmi <image-id>: Remove a Docker image.
 - docker pull <image-name>: Pull an image from a Docker registry (like Docker Hub).
 - docker build -t <image-name>:<tag> .: Build a Docker image from a Dockerfile in the current directory.
## Container Commands:

 - docker ps: List running containers.
 - docker ps -a: List all containers (including stopped ones).
 - docker run <image-name>: Run a container from an image.
 - docker start <container-id>: Start a stopped container.
 - docker stop <container-id>: Stop a running container.
 - docker restart <container-id>: Restart a container.
 - docker rm <container-id>: Remove a stopped container.
## extra
 - docker logs
 - docker inspect
 - docker exec -it <container-id> /bin/sh
 - docker network ls: List all Docker networks.
 - docker network create <network-name>: Create a new network.
 - docker network rm <network-name>: Remove a network.
 - docker volume ls: List all volumes.
 - docker volume create <volume-name>: Create a new volume.
 - docker volume rm <volume-name>: Remove a volume.
 - docker-compose up: Start services defined in a docker-compose.yml file.
 - docker-compose down: Stop and remove all services defined in the docker-compose.yml file.
 - docker-compose logs <service-name>: View the logs of a specific service.
## use -t for name
![image](https://github.com/NghiaDangTran/microservice-research/assets/33323750/39b9ff23-699f-41ff-8a1c-485ed69f3caf)
