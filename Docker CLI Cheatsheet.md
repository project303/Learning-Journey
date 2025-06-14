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

## Managing Containers

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

Delete all stopped containers
```
docker container prune
```

Start a shell inside running containers
```
docker exec -it CONTAINER_NAME EXECUTALE
docker exec -it web bash
```


## Managing Images

Show list of all images
```
docker images
docker image ls	List images
```

Delete an image
```
docker rmi test1:latest
```


## Managing Networks

List all your Docker networks
```
docker network ls
```

Delete a network
```
docker network rm NETWORK_NAME
docker network rm demo-network
```

Delete all unused networks
```
docker network prune
```

To find the IP address
```
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' SERVICE_NAME
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' postgres
```


## Detailed Information

To find all detailed information
```
docker inspect CONTAINER_NAME
docker inspect wordpress
```

To get docker compose directory
```
docker inspect wordpress | grep "com.docker.compose.project.working_dir"
```

To get docker compose file
```
docker inspect wordpress | grep "com.docker.compose.project.config_files"
```
