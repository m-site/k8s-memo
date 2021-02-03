# k8s-memo

## Create a container image
```
cd ${DockerImageName_DIR}
docker build ${DockerImageName} .
```

## Check a container image
```
docker run -d --rm ${DockerImageName} ${ContainerName(Option)} 
docker exec -it ${ContainerName} bash
docker stop ${ContainerName}
```

## git commit
```
git commit -am "${Comment}"
git push
```

## TIPS
### Delete all containers in exited.
```
docker container prune
```

### Delete all containers (including containers in using)
```
docker rm -f $(docker ps -a -q)
```

### Delete all container-images in not using
```
docker image prune
```

### Delete all container-images (including images in using)
```
docker rmi $(docker images -q) -f
```
