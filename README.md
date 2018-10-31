# Index

[Docker Tips and Tricks](#docker-tips-and-tricks)

[Docker Commands](#docker-commands)

[docker attach](#docker-attach)

[docker build](#docker-build) *(Build an image from a Dockerfile)*

[docker exec](#docker-exec)

[docker images](#docker-images)

[docker inspect](#docker-inspect)

[docker logs](#docker-logs)

[docker ps](#docker-ps)

[docker rmi](#docker-rmi)

[docker rm](#docker-rm)

[docker run](#docker-run)

[docker stop](#docker-stop)
    
[Docker Machine Commands](#docker-machine-commands)




# Docker Commands

## [Docker Commands](https://docs.docker.com/engine/reference/commandline/docker/#child-commands)

## [docker attach](https://docs.docker.com/engine/reference/commandline/attach/)
*Attach local standard input, output, and error streams to a running container*


## [docker build](https://docs.docker.com/engine/reference/commandline/build/)
*Build an image from a Dockerfile*
### Usage
```bash
docker build [OPTIONS] PATH | URL | -
```
### Options
    --file,-f       Path where to find the Dockerfile
    --force-rm      Always remove intermediate containers
    --no-cache      Do not use cache when building the image
    --rm            Remove intermediate containers after a successful build (this is true) by default
    --tag,-t        Name and optionally a tag in the ‘name:tag’ format


## [docker exec](https://docs.docker.com/engine/reference/commandline/exec/)
*Run a command in a running container*
### Usage
```sh
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```
### Options
    --detach,-d 		Detached mode: run command in the background
    --detach-keys 		Override the key sequence for detaching a container
    --env,-e            Set environment variables
    --interactive,-i	Keep STDIN open even if not attached
    --privileged 		Give extended privileges to the command
    --tty,-t     		Allocate a pseudo-TTY
    --user,-u    		Username or UID (format: <name|uid>[:<group|gid>])
    --workdir,-w 		Working directory inside the container


## [docker images](https://docs.docker.com/engine/reference/commandline/images/)
*List all downloaded/created images*
### Usage
```sh
docker images [OPTIONS] [REPOSITORY[:TAG]]
```
### Options
    --all,-a 		Show all images (default hides intermediate images)
    --digests 		Show digests
    --filter,-f 	Filter output based on conditions provided
    --format 		Pretty-print images using a Go template
    --no-trunc 		Don’t truncate output
    --quiet,-q 		Only show numeric IDs


## [docker inspect](https://docs.docker.com/engine/reference/commandline/inspect/)
*Return low-level information on Docker objects*
### Usage
```bash
docker inspect [OPTIONS] NAME|ID [NAME|ID...]
```
### Options
    --format,-f     Format the output using the given Go template
    --size,-s       Display total file sizes if the type is container
    --type          Return JSON for specified type


## [docker logs](https://docs.docker.com/engine/reference/commandline/logs/)
*Fetch the logs of a container*
### Usage
```sh
docker logs [OPTIONS] CONTAINER
```
### Options
    --details               Show extra details provided to logs
    --follow,-f             Follow log output
    --since                 Show logs since timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes)
    --tail 	all             Number of lines to show from the end of the logs
    --timestamps,-t         Show timestamps
    --until                 Show logs before a timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes)


## [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
*List containers*
### Usage
```sh
docker ps [OPTIONS]
```
### Options
    --all,-a 		Show all containers (default shows just running)
    --filter,-f 	Filter output based on conditions provided
    --format 		Pretty-print containers using a Go template
    --last,-n    	Show n last created containers (includes all states)
    --latest,-l 	Show the latest created container (includes all states)
    --no-trunc 		Don’t truncate output
    --quiet,-q 		Only display numeric IDs
    --size,-s 		Display total file sizes
        

## [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
*Remove one or more images*
### Usage
```sh
docker rmi [OPTIONS] IMAGE [IMAGE...]
```
### Options
    --force,-f 		Force removal of the image
    --no-prune 		Do not delete untagged parents


## [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
*Remove one or more containers*
### Usage
```sh
docker rm [OPTIONS] CONTAINER [CONTAINER...]
```
### Options
    --force,-f 		Force the removal of a running container (uses SIGKILL)
    --link,-l 		Remove the specified link
    --volumes,-v 	Remove the volumes associated with the container


## [docker run](https://docs.docker.com/engine/reference/commandline/run/)
*Run a command in a new container*
### Usage
```sh
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```
### [Options](https://docs.docker.com/engine/reference/commandline/run/#options)
    

## [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
*Stop one or more running containers*
### Usage
```sh
docker stop [OPTIONS] CONTAINER [CONTAINER...]
```
### Options
    --time,-t   Seconds to wait for stop before killing it

------------------------------------------------------------------------------------------------------------------------
# Docker Machine Commands

## [Docker Machine Reference](https://docs.docker.com/machine/reference/)


## [docker-machine active](https://docs.docker.com/machine/reference/active/)


## [docker-machine create](https://docs.docker.com/machine/reference/create/)

------------------------------------------------------------------------------------------------------------------------
# Docker Tips and Tricks
A collection of useful tips and tricks for Docker.

## Stop all containers
**NOTE:** This will stop ALL your containers.
```sh
docker stop $(docker ps -aq)
```

## Remove all containers
**NOTE:** This will remove ALL your containers.
```sh
docker rm $(docker ps -a -q)
```

## Remove all images
**NOTE:** This will remove ALL your images.
```sh
docker rmi $(docker images -q)
```

## Stop and remove all images and containers
**NOTE:** This will remove ALL your images/containers.
```sh
docker stop $(docker ps -aq) && docker rm $(docker ps -aq) && docker rmi $(docker images -q)
```

## Remove all untagged containers
```sh
docker rmi $(docker images | grep '^<none>' | awk '{print $3}')
```

## Connect to a docker container
```sh
sudo docker exec -i -t [CONTAINER ID] /bin/bash
```

## See all space Docker take up
```sh
docker system df
```

## Get IP address of running container
```sh
docker inspect [CONTAINER ID] | grep -wm1 IPAddress | cut -d '"' -f 4
```

## Kill all running containers
```sh
docker kill $(docker ps -q)
```

