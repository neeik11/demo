# Installation
- Login with root (connect Internet)
```su -
   curl -sSL https://get.docker.com/ | sudo sh
```

- Grant permission for user
> sudo usermod -aG docker `whoami`

- Enable and start docker service 
> systemctl start docker.service
> systemctl enable docker.service
> systemctl status docker.service

- Check docker version
> docker version

- Test run docker
> docker pull hello-world
> docker run hello-world
