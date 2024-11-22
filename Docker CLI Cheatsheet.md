# Docker CLI Cheatsheet

## Run a New Container

Start a new container from an image
```
docker run IMAGE_NAME
docker run nginx
```

.. and assign it name
```
docker run --name CONTAINER_NAME IMAGE_NAME
docker run --name web nginx
```

.. and map a port
```
docker run -p HOSTPORT:CONTAINER_PORT IMAGE_NAME
docker run -p 8080:80 nginx
```

.. and start container in background
```
docker run -d IMAGE_NAME
docker run -d nginx
```

## Manage Containers

Show list of running containers
```
docker ps
```

Show list of all containers
```
docker ps -a
```

Start a stopped container
```
docker start CONTAINER_NAME
docker start web
```

Stop a running container
```
docker stop CONTAINER_NAME
docker stop web
```

Delete a container
```
docker rm CONTAINER_NAME
docker rm web
```

Delete a running container
```
docker rm -f CONTAINER_NAME
docker rm -f web
```

Delete stopped containers
```
docker rm prune
```

Start a shell inside running containers
```
docker exec -it CONTAINER_NAME EXECUTALE
docker exec -it web bash
```



## Manage Images

Show list of all images
```
docker images
```

