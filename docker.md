# Docker Commands and Their Usage
## Basic Commands
### Docker Version
```sh
docker --version
```
Show the Docker version information.

### Docker Info
`sh
Copy code
`
docker info
Display system-wide information.

### Docker Help
`sh
docker --help
`
Show help for Docker commands.

### Container Management
Run a Container
`sh
docker run <image>`
Run a container from an image.

### Run a Container in Detached Mode
`sh
docker run -d <image>`
Run a container in the background and print the container ID.

### Run a Container with Port Mapping
```sh
docker run -p <host_port>:<container_port> <image>
```
Run a container with port mapping.

### Run a Container with a Specific Name
```sh
docker run --name <container_name> <image>
```
Run a container with a specific name.
### Run a Container with a Volume
```sh
docker run -v <host_path>:<container_path> <image>
```
Run a container with a volume.

### Run a Container with Environment Variables
```sh
docker run -e <env_var>=<value> <image>
```
Run a container with environment variables.

### List Running Containers
```sh
docker ps
```
List all running containers.

### List All Containers
```sh
docker ps -a
```
List all containers, including stopped ones.

### Stop a Container
```sh
docker stop <container_id>
```
Stop a running container.

### Start a Container
```sh
docker start <container_id>
```
Start a stopped container.

### Restart a Container
```sh
docker restart <container_id>
```
Restart a container.

### Remove a Container
```sh
docker rm <container_id>
```
Remove a container.

### Remove All Stopped Containers
```sh
docker container prune
```
Remove all stopped containers.

### Inspect a Container
```sh
docker inspect <container_id>
```
Display detailed information about a container.

### View Container Logs
```sh
docker logs <container_id>
```
Fetch the logs of a container.

### Execute a Command in a Running Container
```sh
docker exec -it <container_id> <command>
```
Execute a command in a running container.

### Attach to a Running Container
```sh
docker attach <container_id>
```
Attach to a running container.

### Image Management
List Docker Images
```sh
docker images
```
List all Docker images.

### Pull an Image from a Registry
```sh
docker pull <image>
```
Pull an image from a Docker registry.

### Push an Image to a Registry
```sh
docker push <image>
```
Push an image to a Docker registry.

### Build an Image from a Dockerfile
```sh
docker build -t <image_name> <path>
```
Build an image from a Dockerfile.

### Remove an Image
```sh
docker rmi <image_id>
```
Remove an image.

### Remove All Unused Images
```sh
docker image prune
```
Remove all unused images.

### Tag an Image
```sh
docker tag <source_image> <target_image>
```
Tag an image.

### Save an Image to a Tar Archive
``` sh
docker save -o <path> <image>
```
Save an image to a tar archive.

### Load an Image from a Tar Archive
```sh
docker load -i <path>
```
Load an image from a tar archive.

### Network Management
List Docker Networks
```sh
docker network ls
```
List all Docker networks.

### Create a Docker Network
```sh
docker network create <network_name>
```
Create a new Docker network.

### Inspect a Docker Network
```sh
docker network inspect <network_name>
```
Display detailed information about a network.

### Connect a Container to a Network
```sh
docker network connect <network_name> <container_id>
```
Connect a container to a network.

### Disconnect a Container from a Network
```sh
docker network disconnect <network_name> <container_id>
```
Disconnect a container from a network.

### Remove a Docker Network
```sh
docker network rm <network_name>
```
Remove a Docker network.

### Volume Management
List Docker Volumes
```sh
docker volume ls
```
List all Docker volumes.

### Create a Docker Volume
```sh

docker volume create <volume_name>
```
Create a new Docker volume.

### Inspect a Docker Volume
```sh
docker volume inspect <volume_name>
```
Display detailed information about a volume.

### Remove a Docker Volume
```sh
docker volume rm <volume_name>
```
Remove a Docker volume.

### Remove All Unused Volumes
```sh
docker volume prune
```
Remove all unused volumes.

## Docker Compose Commands
Docker Compose Up
```sh
docker-compose up
```
Create and start containers defined in a docker-compose.yml file.

### Docker Compose Up in Detached Mode
```sh
docker-compose up -d
```
Create and start containers in detached mode.

### Docker Compose Down
```sh
docker-compose down
```
Stop and remove containers, networks, images, and volumes defined in a docker-compose.yml file.

### Docker Compose Build
```sh
docker-compose build
```
Build or rebuild services defined in a docker-compose.yml file.

### Docker Compose Logs
```sh
docker-compose logs
```
View output from containers defined in a docker-compose.yml file.

### Docker Compose Exec
```sh
docker-compose exec <service_name> <command>
```
Execute a command in a running container of a service.

### Docker Compose Stop
```sh
docker-compose stop
```
Stop services defined in a docker-compose.yml file.

### Docker Compose Start
```sh
docker-compose start
```
Start services defined in a docker-compose.yml file.

### Docker Compose Pull
```sh
docker-compose pull
```
Pull service images defined in a docker-compose.yml file.

### Docker Compose Ps
```sh
docker-compose ps
```
List containers defined in a docker-compose.yml file.