# k8s-memo

## Create container image
```
cd ${DockerImageName_DIR}
docker build ${DockerImageName} .
```

## Check container image
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
### Delete all exited container
```
docker container prune
```

### Delete all container (including running container)
```
docker rm -f $(docker ps -a -q)
```

### Delete all unused container image
```
docker image prune
```

### Delete all container image(including using image)
```
docker rmi $(docker images -q) -f
```
