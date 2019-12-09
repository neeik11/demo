# Create DockerFile
- Used image
```
FROM ubuntu:14.04
```

- Owner
```
MAINTAINER kiennt
```

- Commands
```
RUN apt-get update -y && ap-get install apache2 && apt-get clean && rm-rf /var/lib/apt/lists/*
```

- Env variables
```
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid
ENV APACHE_RUN_DIR /var/run/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_SERVERADMIN admin@localhost
ENV APACHE_SERVERNAME localhost
ENV APACHE_SERVERALIAS docker.localhost
ENV APACHE_DOCUMENTROOT /var/www
```

- Port used by apache service 
```
EXPOSE 80
```

- Command execute by app in container
```
CMD ["/usr/bin/apache2", "-D", "FOREGROUND"]
```

- Create script file 
```
#!/bin/bash
mkdir -p apache && cd apache

cat << EOF > dockerfile
FROM ubuntu:14.04

MAINTAINER kiennt

RUN apt-get update && apt-get install -y apache2 && apt-get clean && rm -rf /var/lib/apt/lists/*

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid
ENV APACHE_RUN_DIR /var/run/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_SERVERADMIN admin@localhost
ENV APACHE_SERVERNAME localhost
ENV APACHE_SERVERALIAS docker.localhost
ENV APACHE_DOCUMENTROOT /var/www

EXPOSE 80

CMD ["/usr/sbin/apache2", "-D", "FOREGROUND"]
EOF

docker build -t apache_test
```

- Create image using dockerfile
```
bash dockerfile.sh
```

