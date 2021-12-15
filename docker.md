### Systemctl Commands

`sudo systemctl disable --now docker.service docker.socket`
`sudo systemctl start`
`sudo systemctl enable --now docker`

### Docker Group Users

- Add docker group: `sudo groupadd docker`
- Add current user to the docker group: `sudo gpasswd -a $USER docker`
- Refresh group users: log out/in or run: `newgrp docker`

#### Get Docker Group Users

`getent group docker`

### Docker

`docker ps -a` -> shows running/dead containers, docker images show what images you have
docker sets up a process in a different kernel namespace and connects it to a virtual network and sets up disk mounts etc

#### Docker Images

`docker pull <container name>`

- Create and run container named test from the latest ubuntu image

```
docker run --name test -it ubuntu
```

#### Docker Containers

- `docker images` -> all the docker images on your machine
- `docker ps` -> list down all running docker containers
- `docker ps -a` -> list down all the docker containers
- `docker start <container name or id>` -> start a container
- `docker stop <container name or id>` -> stop a container
- `docker run <image name or id>` -> create a container using a docker image

docker pull nginx:1-alpine && docker run --rm -p 5055:80 -ti nginx:1-alpine
-> -p <HOST PORT>:<CONTAINER PORT>
-> --rm -> clean it up after you stop the container
i actually do like -p 192.168.221.50:80:22 in one case

### Dockerizing a Full Stack Application

https://siddharth-lakhara.medium.com/dockerizing-a-full-stack-js-app-ceb99411996e

- create dockerfiles in backend & frontend
- use docker compose to tie the containers together as a single application

#### Docker Compose

write a file called `docker-compose.yml`
It can be as simple as:

```yml
services:
  frontend:
    build: ./frontend
    ports:
      - "3000:3000"
    depends_on:
      - backend
  backend:
    build: ./backend
    ports:
      - "6969:6969"
```

Essentially what you're doing here is you're mapping the ports from the container to the host so that you can access these ports with localhost.
For example, I wrote the wrong ports for backend and it meant that I couldn't resolve any API requests using `http://localhost:6969`.
also, this requires you to have a Dockerfile in your frontend and backend folders with the docker-compose file in the root project directory.

### Docker Cleanup

- remove containers: `docker rm <container_id>`
- remove images: `docker rmi <image_name/image_id>`

## Questions

- if I'm in a github repo that uses docker, am I pulling the docker image from the repo?
  -> Look at [docker files](https://docs.docker.com/engine/reference/commandline/build/)...
  - Typically, you would download the Dockerfile, then run `docker build <dockerfile path or url>` in the target directory (e.g. frontend) to build an image from the Dockerfile. From there you could do `docker run -p <host_port>:<container_port> <image_name/image_id>` or
- if I'm running a docker container with an Ubuntu image on a Windows machine, what do commands look like? What's supported????

```
docker pull quay.io/authzed/spicedb:latest
docker run quay.io/authzed/spicedb serve --grpc-preshared-key "somerandomkeyhere" --grpc-no-tls --http-no-tls
```

`docker exec -ti charming_merkle bash`
docker inspect quay.io/authzed/spicedb

- in the first line of dockerfile, where can I find what I should put `FROM node:alpine3.11`

  - You can do `FROM node:latest` for a frontend/backend that uses node. You basically just want to use the latest docker image for the tools you need so you don't have to start from scratch

- what is "/app" directory for a Dockerfile?

  - `WORKDIR /myapp` is where your docker config files will live in the container. Using this replaces the need to use `RUN mkdir /app`. Your docker build command
  - [source](https://nickjanetakis.com/blog/docker-tip-46-using-workdir-to-cleanup-your-dockerfile)

- Do you need to delete a docker container if you make changes to the dockerfile?

  - I think so because it would be built off of the previous version of the dockerfile
  - Yes, you'll want to remove the containers and images when changes to directory's Dockerfile are made. Which is why there are commands to run, then clean up the containers automagically.

- why do I need to `COPY package*.json ./` AND `COPY . .` wouldn't the latter copy the package.json files anyway?
  [dockerize mern stack application - this is very helpful!](https://suraj-patel.medium.com/dockerize-mern-stack-application-9ea8de68ea4e)

  - from what I've seen, it does copy the package\*.json files when you do `COPY . .`

- how do you create a successful request to a containerized backend?
  - be sure to map the ports in your `docker-compose.yml`, then you can access it normally.
