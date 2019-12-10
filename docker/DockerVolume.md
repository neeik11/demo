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


