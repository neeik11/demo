# Docker Volume
## Bind mount
- Create a container using bind mount
```
mkdir -p /root/web_test && cd /root/web_test
docker run --name apache-test2 -p 8080:80 -p 443:443 -v /root/web_test/:/var/www/ -d eboraas/apache
```

- Check mounted volume
```
docker inspect -f '{ .Mounts }' apache_test2
or docker inspect apache_test2
```

- Test bind mount
```
touch local_file
docker exec apache_test2 ls /var/www/
```

## Docker managed volume
- Create volume
```
docker volume create --name avolume
```

- Check volume
```
docker volume inspect avolume
```

- Run container with avolume mounted
```
docker run --name apache_test3 -p 8080:80 -p 443:443 -v avolume:/var/www/ -d eboraas/apache
```

- Check volume after mount
```
docker inspect -f '{{ .Mounts }}' apache_test3
or docker inspect apache_test3
```
