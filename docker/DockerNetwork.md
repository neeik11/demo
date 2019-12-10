# Docker network
- List docker networks
```
docker network ls
```

- Show information docker network
```
docker network inspect bridge
```

- Create bridge network with specified subnet
```
docker network create --driver=bridge --subnet=192.168.100.0/24 my-net1
```

- Run a container with specified network
```
docker run --network=ny-net1 -d httpd
```
