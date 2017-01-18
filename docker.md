# Docker CheatSheet

### Images
```
docker pull fedora:22 # pull fedora image v.22
docker pull redis:latest # pull redis last version
docker images # list images
docker tag <image_id> <tag_name>
docker history <tag_name>
```

### Build
```
docker build .
docker build -t <name:tag> . # better
```

### Create/Run
```
docker run --rm -p 80:80 <name:tag>
docker run --rm -p 80:80 <name:tag> --name <desired_name>
docker run --rm -ti <name:tag> /bin/bash # open bash and then delete container
docker create <name:tag>
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

### Basic structure
```
version: '2'
services:
  web:
    build: .
    restart: unless-stopped
    volumes:
          - ./web:/server/http
    ports:
      - "80:80"
#      - "443:443"
#    links:
#      - redis
    environment:
      DEBUG: 'true'
```

### Commands

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
docker-machine start testing
docker-machine stop testing
docker-machine regenearte-certs testing
```
