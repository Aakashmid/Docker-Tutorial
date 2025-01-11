# Docker Commands

## Container Management
- `docker run <image>` - Create and start a new container from an image
- `docker start <container>` - Start an existing stopped container
- `docker stop <container>` - Stop a running container
- `docker restart <container>` - Restart a container
- `docker rm <container>` - Remove a stopped container
- `docker ps` - List running containers
- `docker ps -a` - List all containers (running and stopped)

## Image Management
- `docker images` - List all local images
- `docker pull <image>` - Download an image from Docker Hub
- `docker push <image>` - Upload an image to Docker Hub
- `docker rmi <image>` - Remove a local image
- `docker build -t <name:tag> .` - Build an image from a Dockerfile

## Container Interaction
- `docker exec -it <container> bash` - Open interactive shell in container
- `docker logs <container>` - View container logs
- `docker cp <src> <container>:<dest>` - Copy files between host and container
- `docker inspect <container>` - View detailed container information

## Network Management
- `docker network create <network>` - Create a network
- `docker network ls` - List all networks
- `docker network connect <network> <container>` - Connect container to network

## Volume Management
- `docker volume create <volume>` - Create a volume
- `docker volume ls` - List all volumes
- `docker volume rm <volume>` - Remove a volume

## System Management
- `docker system prune` - Remove unused data (containers, images, networks)
- `docker stats` - Show live container resource usage
- `docker info` - Display system-wide information

## Environment Variables
- `docker run -e KEY=value` - Set environment variable in container
- `docker run --env-file=<file>` - Load environment variables from file
- `docker inspect -f '{{.Config.Env}}' <container>` - View container environment variables
- `docker run -e MYSQL_ROOT_PASSWORD=password` - Example setting database password
- `docker run --env-file=.env` - Load variables from .env file



----



# Example of creating container from image passing environment variables
### Run a Django container
docker run --name simple-django2 -p 8000:8000 -e MAGIC_MESSAGE="Hello from Docker!" docker-simple

` --name: assigns name 'simple-django2' to container
` -p 8000:8000: maps host port 8000 to container port 8000
` -e: sets environment variable MAGIC_MESSAGE
` docker-simple: name of the image to run

### View the running container
docker ps

### Stop the container
docker stop simple-django2

### Remove the container
docker rm simple-django2

### View container logs
docker logs simple-django2

### Execute into container shell
docker exec -it simple-django2 bash

### Copy files to container
docker cp ./local-file.txt simple-django2:/app/

### View container details
docker inspect simple-django2

### View container environment variables
docker inspect -f '{{.Config.Env}}' simple-django2

### View container resource usage
docker stats simple-django2