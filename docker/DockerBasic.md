# Installation
- Login with root (connect Internet)
```
su -
curl -sSL https://get.docker.com/ | sudo sh
```

- Grant permission for user
```
sudo usermod -aG docker `whoami`
```

- Enable and start docker service 
```
systemctl start docker.service
systemctl enable docker.service
systemctl status docker.service
```

- Check docker version
```
docker version
```

- Test run docker
```
docker pull hello-world
docker run hello-world
```

# Docker basic
## Docker containers
- Run a container
```
docker run busybox echo 'Hello World'
docker run busybox whoami
docker run busybox route
```

- Run a container in interaction mode
```
docker run -it busybox
```

- Run a container in daemon mode
```
docker run -d httpd
```

- List containers
```
# List all containers
docker ps -a 

# List containers running
docker ps
```

- Name container
```
docker run --name <name> <imagename>
```

- Run a container with specified port
```
# Map port 4000(host) to 80(container)
docker run -d -p 4000:80 httpd

# Map port random for container
docker run -d -P nginx
```

- Run an existing container using terminal
```
docker exec -it <container ID/name> /bin/bash
```

- Assign RAM & CPU for container
```
docker run -d -p 4000:80 --name webserver --memory 400m --cpus 0.5 httpd
```

- Show content, log & port of container
```
docker inspect <container ID/name>
docker logs -f <container ID/name>
docker port <container ID/name>
```

- Delete containers
```
docker rm <container ID/name>
docker rm -f <container ID/name>
```

- Delete all containers on host
```
docker rm -f $(docker ps -aq)
```

- Commit a container to image
```
docker commit <containername> <imagename>
```

- Start, stop & restart container
```
docker [restart | stop | start] <containername>
```

## Docker images
- Search images
```
docker search <imagename>
```

- Download image
```
docker pull <imagename>
```

- List all images
```
docker images
```

- Show image information 
```
docker image inspect <imagename>
```

- Show history commit of image
```
docker history <imagename>
```

- Delete image
```
docker rmi <imagename>
```

- Change image tag 
```
docker tag <imagename> <tagname>
```


