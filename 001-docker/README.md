# Requirements
- local docker daemon installed and accessible by terminal commands
- internet connection DO NOT USE TRAFFIC LIMITED CONNECTIONS!
- if you want to use these images remotely you need to push them to a registry

These commands were tested on MacOS Catalina with Docker Desktop 2.2.0.3

# Docker commands
Build the docker image
```
docker build -t webmeetup:latest .
```

Show available docker images on local daemon
```
docker images
```

Show layer sizes 
```
docker history <docker-image-id>
```

Delete unused images in a single command
```
for ID in `docker images | grep none |awk '{print $3}'`; do docker rmi ${ID};  done
```

Delete stopped containers from daemon in a single command
```
for ID in `docker ps -a |grep -v CONTAINER|awk '{print $1}'`; do docker rm ${ID}; done
```

Tag existing docker image
```
docker tag webmeetup:latest webmeetup:newTag
```

Remove existing tag but keeping the image if needed
```
docker rmi webmeetup:latest
```

Login to remote docker registry
```
docker login <registryurl>
```

Copy local image to remote registry
```
docker tag webmeetup:latest <registryurl>/webmeetup:latest
docker push <registryurl>/webmeetup:latest
```
Pull docker image from remote registry
```
docker pull <registryurl>/webmeetup:latest
```
