# Docker Commands
## [Docker Commands](https://docs.docker.com/engine/reference/commandline/docker/#child-commands)

### [docker attach](https://docs.docker.com/engine/reference/commandline/attach/)
*Attach local standard input, output, and error streams to a running container*

### [docker build](https://docs.docker.com/engine/reference/commandline/build/)
*Build an image from a Dockerfile*
#### Usage
```bash
docker build [OPTIONS] PATH | URL | -
```
#### Options
    --file,-f       Path where to find the Dockerfile
    --force-rm      Always remove intermediate containers
    --no-cache      Do not use cache when building the image
    --rm            Remove intermediate containers after a successful build (this is true) by default
    --tag,-t        Name and optionally a tag in the ‘name:tag’ format

### [docker exec](https://docs.docker.com/engine/reference/commandline/exec/)
*Run a command in a running container*
#### Usage
```bash
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```
#### Options
    --detach -d Detached mode: run command in the background
    -it This will not make the container you started shut down immediately, as it will create a pseudo-TTY session (-t) and keep STDIN open (-i)
#### How to conect to a docker container
```bash
sudo docker exec -i -t [CONTAINER ID] /bin/bash
```

### [docker images](https://docs.docker.com/engine/reference/commandline/images/)
*List all downloaded/created images*
#### Usage
```bash
docker images [OPTIONS] [REPOSITORY[:TAG]]
```
#### Options
    -q Only show numeric IDs

### [docker inspect](https://docs.docker.com/engine/reference/commandline/inspect/)
*Return low-level information on Docker objects*
#### Usage
```bash
docker inspect [OPTIONS] NAME|ID [NAME|ID...]
```
#### Options
    --format,-f     Format the output using the given Go template
    --size,-s       Display total file sizes if the type is container
    --type          Return JSON for specified type

### [docker logs](https://docs.docker.com/engine/reference/commandline/logs/)
*Fetch the logs of a container*
#### Usage
```bash
docker logs [OPTIONS] CONTAINER
```
#### Options
    --details               Show extra details provided to logs
    --follow,-f             Follow log output
    --since                 Show logs since timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes)
    --tail 	all             Number of lines to show from the end of the logs
    --timestamps,-t         Show timestamps
    --until                 Show logs before a timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes)

### [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
*List containers*
#### Usage
```bash
docker ps [OPTIONS]
```
#### Options
    --all,-a 		Show all containers (default shows just running)
    --filter,-f 	Filter output based on conditions provided
    --format 		Pretty-print containers using a Go template
    --last,-n    	Show n last created containers (includes all states)
    --latest,-l 	Show the latest created container (includes all states)
    --no-trunc 		Don’t truncate output
    --quiet,-q 		Only display numeric IDs
    --size,-s 		Display total file sizes
        
### [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
*Remove one or more images*
#### Usage
```bash
docker rmi [OPTIONS] IMAGE [IMAGE...]
```
#### Options
    --force,-f 		Force removal of the image
    --no-prune 		Do not delete untagged parents

### [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
*Remove one or more containers*
#### Usage
```bash
docker rm [OPTIONS] CONTAINER [CONTAINER...]
```
#### Options
    --force,-f 		Force the removal of a running container (uses SIGKILL)
    --link,-l 		Remove the specified link
    --volumes,-v 	Remove the volumes associated with the container

### [docker run](https://docs.docker.com/engine/reference/commandline/run/)
*Run a command in a new container*
#### Usage
```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```
#### [Options](https://docs.docker.com/engine/reference/commandline/run/#options)
    

### [docker stop](https://docs.docker.com/engine/reference/commandline/stop/) | ( Stop one or more running containers )
### Stop all containers
```bash
docker stop $(docker ps -aq)
```
### Delete all images and containers
```bash
docker stop $(docker ps -aq) && docker rm $(docker ps -aq) && docker rmi $(docker images -q)
```

------------------------------------------------------------------------------------------------------------------------
# Docker Machine Commands
## [Docker Machine Reference](https://docs.docker.com/machine/reference/)

### [docker-machine active](https://docs.docker.com/machine/reference/active/)
### [docker-machine create](https://docs.docker.com/machine/reference/create/)
