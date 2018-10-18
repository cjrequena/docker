# Docker Commands
## [Docker Commands](https://docs.docker.com/engine/reference/commandline/docker/#child-commands)

### [docker attach](https://docs.docker.com/engine/reference/commandline/attach/) | ( Attach local standard input, output, and error streams to a running container )

### [docker build](https://docs.docker.com/engine/reference/commandline/build/) | ( Build an image from a Dockerfile )

### [docker exec](https://docs.docker.com/engine/reference/commandline/exec/) | ( Run a command in a running container )
#### Conect to a docker container
```bash
sudo docker exec -i -t dd-agent /bin/bash
```

### [docker rm](https://docs.docker.com/engine/reference/commandline/rm/) | ( Remove one or more containers )
#### Delete all containers
```bash
docker rm $(docker ps -aq)
```

### [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/) | ( Remove one or more images )
#### Delete all images
```bash
docker rmi $(docker images -q)
```

### [docker stop](https://docs.docker.com/engine/reference/commandline/stop/) | ( Stop one or more running containers )
### Stop all containers
```bash
docker stop $(docker ps -aq)
```

### Delete all images and containers
```bash
docker stop $(docker ps -aq) && docker rm $(docker ps -aq) && docker rmi $(docker images -q)
```

# Docker Machine Commands
## [Docker Machine Reference](https://docs.docker.com/machine/reference/)

### [docker-machine active](https://docs.docker.com/machine/reference/active/)
### [docker-machine create](https://docs.docker.com/machine/reference/create/)
