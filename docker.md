# Docker CheatSheet

### Images
```
docker pull fedora:22 # pull fedora image v.22
docker pull redis:latest # pull redis last version
docker images # list images
docker tag <image_id> <tag_name>
docker history <tag_name>
```

### Build/run
```
docker build .
docker build -t <name:tag> . # better
docker run --rm -ti docker-php70:latest /bin/bash # open bash and then delete container
```

### Listing
```
docker ps # list containers
docker ps -a # list all containers
docker ps -aq # Only display numeric IDs
```

### Destroy/Delete
```
docker kill <container_hash>
docker rm <container_hash>
```

### export
```
docker export <container_hash> > export.tar
```

## Docker Compose
```
docker-compose build
docker-compose up -d
docker-compose stop
```

## Docker Hub
```
docker login
```

### Create Image and push
```
export HUB_USER=${USER}
docker images
docker build -t ${HUB_USER}/mybot:latest .
docker images
docker search ${HUB_USER}/mybot
docker push ${HUB_USER}/mybot:latest
docker search ${HUB_USER}/mybot
```

## Docker Machine

### Create/Start
```
docker-machine create --driver virtualbox --virtualbox-cpu-count "2" testing
    * (or) docker-machine start testing
eval $(docker-machine env testing)
```

### Basic Commands
```
docker-machine ls
docker-machine ip testing
docker-machine ssh testing
docker-machine stop testing
```
