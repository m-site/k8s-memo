# k8s-memo

## How to build container image

### Create Github Repository
```
(create Github repo)
cd ${GIT_DIR}
git clone ${REPO_URL}
```

### Create a container image
```
cd ${DockerImageName_DIR}
(create Dockerfile)
docker build -t ${DockerImageName} .
```

### Check a container image
```
docker run -d --rm ${DockerImageName} ${ContainerName(Option)} 
docker exec -it ${ContainerName} bash
docker stop ${ContainerName}
```

### git commit (work with DockerHub)
```
git commit -am "${Comment}"
git push
```

## TIPS(docker)

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

## TIPS(kubectl)
### Install kubectl
```
sudo apt install kubectl
echo 'alias k="kubectl"'
```

### KUBECONFIG switching settings
```
# Install direnv
sudo apt install direnv

# Create a directory with the target ns name
mkdir ${NS_DIR}

# Download and Copy kubeconfig file
e.g. cp kubeconfig.yaml ${NS_DIR}/.

# Create .envrc
echo 'export KUBECONFING=${NS_DIR}/kubeconfig.yaml' > ${NS_DIR}/.envrc

# Check direnv setting
cd ${NS_DIR}
 or
re-login

direnv allow

# Check kubectl context
kubectl config current-context
 or
kubectl config get-contexts

# Check the name of the Namespace you are accessing
kubectl get ns
```
