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

## Manage Images

Show list of all images
```
docker images
```

