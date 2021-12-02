
### Systemctl Commands	
`sudo systemctl disable --now docker.service docker.socket`
`sudo systemctl start`	
`sudo systemctl enable --now docker`

### Get Docker Group Users
`getent group docker`

### Docker
`docker ps -a` -> shows running/dead containers, docker images show what images you have
docker sets up a process in a different kernel namespace and connects it to a virtual network and sets up disk mounts etc

#### Must Know Docker Commands

-   `docker images` -> all the docker images on your machine
-   `docker ps` -> list down all running docker containers
-   `docker ps -a` -> list down all the docker containers
-   `docker start <container name or id>` -> start a container
-   `docker stop <container name or id>` -> stop a container
-   `docker run <image name or id>` -> create a container using a docker image

docker pull nginx:1-alpine && docker run --rm -p 5055:80 -ti nginx:1-alpine
-> -p <HOST PORT>:<CONTAINER PORT>
-> --rm -> clean it up after you stop the container
i actually do like -p 192.168.221.50:80:22 in one case

## Questions
- if I'm in a github repo that uses docker, am I pulling the docker image from the repo?
	-> Look at docker files...
- if I'm running a docker container with an Ubuntu image on a Windows machine, what do commands look like? What's supported????  
	
```
docker pull quay.io/authzed/spicedb:latest
docker run quay.io/authzed/spicedb serve --grpc-preshared-key "somerandomkeyhere" --grpc-no-tls --http-no-tls
```
	
`docker exec -ti charming_merkle bash`
docker inspect quay.io/authzed/spicedb
