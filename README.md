# Docker Commands
## [Docker Commands](https://docs.docker.com/engine/reference/commandline/docker/#child-commands)

### Stop all containers
```bash
docker stop $(docker ps -aq)
```

### Delete all containers
```bash
docker rm $(docker ps -aq)
```

### Delete all images
```bash
docker rmi $(docker images -q)
```

### Delete all images and containers
```bash
docker stop $(docker ps -aq) && docker rm $(docker ps -aq) && docker rmi $(docker images -q)
```

### Conect to a docker container
```bash
sudo docker exec -i -t dd-agent /bin/bash
```

# Docker Machine Commands
## [Docker Machine Reference](https://docs.docker.com/machine/reference/)

### Create a default docker machine
```bash
docker-machine create -d virtualbox default
```

### Create a docker-machine with a specific IP
```bash
docker-machine create -d virtualbox --virtualbox-hostonly-cidr "192.168.10.1/24" docker-machine-name
```

### Configure shell environment to connect to your new Docker instance
```bash
eval "$(docker-machine env default)"
```