# Docker Compose
Helps you manage Docker images

## Build the image

`$ docker-compose build`

## Once the image is built, run the container

`$ docker-compose up -d`


# Docker Commands

## docker search
We can use the command docker search to search for public images on the Docker hub. It will return information about the image name, description, stars, official and automated.

`docker search MySQL`

## docker pull
Now that we know the name of the image, we can pull that from the Docker hub using the command docker pull. Here, we are setting the platform option as well.

`docker pull --platform linux/x86_64 mysql`

Tags are used to identify images inside a repository. If we don’t specify a tag Docker engine uses the :latest tag by default. So, in the previous example, Docker pulled the mysql:latest image.

If our application depends on a specific version of an image, we can specify that using a tag name.

`docker pull --platform linux/arm64/v8 mysql:5.6`

## docker images
Brilliant, now we should have some images in our local machine, and to confirm, let’s run the following command to list all the local images.

`docker images`

## docker run
Alright, now that we have some images, we can try to create a container. Here we used the --env option to set a mandatory environment variable and --detach option to run the container in the background.

`docker run --env MYSQL_ROOT_PASSWORD=my-secret-pw --detach mysql`

Moreover, we can use the --name option to assign a name to the container. Docker will randomly assign a name if we don’t provide one.

## docker ps
We can list all the running containers by using the following command.

`docker ps`

How about listing all the containers, including the stopped ones? We can do that by adding --all option.

`docker ps --all`

## docker stop
To stop a container, use the docker stop command with either the container id or container name. We may stop a container if we want to change our docker run command.

`docker stop f8c52bedeecc`

## docker restart
Let’s restart our stopped contained by using the following command. We may want to use this after we reboot our machine.

`docker restart f8c52bedeecc`

## docker rename
Now, let’s change the container name from compassionate_fermi to test_db. We may want to change the name to keep track of our containers more easily.

`docker rename compassionate_fermi test_db`

## docker exec
Access the running container test_db by running the following command. It’s helpful if we want to access the MySQL command line and execute MySQL queries.
```
docker exec -it test_db bash
mysql -uroot -pmy-secret-pw
SHOW DATABASES;
```
The -i and -t options are used to access the container in an interactive mode. Then we provide the name of the container we want to access, which in this case test_db. Finally, the bash command is used to get a bash shell inside the container.

## docker logs
This command is helpful for debugging our Docker containers. It will fetch logs from a specified container.

`docker logs test_db`  

If we want to continue to stream new output, we can use the option -follow.

`docker logs -follow test_db`

## docker rm
If we want to remove a container (ie an instance of an docker image)  we can use the following command.

`docker rm test_db`

You may encounter an error like
Error response from daemon: You cannot remove a running container ……… Stop the container before attempting removal or force remove

As it recommends, we can stop the container first and then remove it or use the option -f to remove a running container forcefully.
```
docker stop test_db
docker rm test_db
# or
docker rm -f test_db
```

## docker rmi
Finally, if we want to free some disk space, we can use the docker rmi command with the image id to remove an image.

`docker rmi eb0e825dc3cf`

