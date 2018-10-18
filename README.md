# Docker Commands
## [Docker Commands](https://docs.docker.com/engine/reference/commandline/docker/#child-commands)

### [docker exec](https://docs.docker.com/engine/reference/commandline/exec/) Run a command in a running container
#### Conect to a docker container
```bash
sudo docker exec -i -t dd-agent /bin/bash
```

### [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
### Stop all containers
```bash
docker stop $(docker ps -aq)
```

### [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
#### Delete all containers
```bash
docker rm $(docker ps -aq)
```

### [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
#### Delete all images
```bash
docker rmi $(docker images -q)
```

### Delete all images and containers
```bash
docker stop $(docker ps -aq) && docker rm $(docker ps -aq) && docker rmi $(docker images -q)
```


# Docker Machine Commands
## [Docker Machine Reference](https://docs.docker.com/machine/reference/)

### [docker-machine active](https://docs.docker.com/machine/reference/active/)
### [docker-machine create](https://docs.docker.com/machine/reference/create/)
