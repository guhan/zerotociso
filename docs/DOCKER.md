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



# DockerFile

## FROM
Usage:
```
FROM <image>
FROM <image>:<tag>
FROM <image>@<digest>
FROM <image> as “use_me_later”
```
Information:
-  FROM must be the first non-comment instruction in the Dockerfile.
-  FROM can appear multiple times within a single Dockerfile in order to create multiple images. Simply make a note of the last image ID output by the commit before each new FROM command.
-  The tag or digest values are optional. If you omit either of them, the builder assumes a latest by default. The builder returns an error if it cannot match the tag value.


## MAINTAINER
Usage:
```
MAINTAINER <name>
```
The MAINTAINER instruction allows you to set the Author field of the generated images.


## RUN
Usage:
```
RUN <command> (shell form, the command is run in a shell, which by default is /bin/sh -c on Linux or cmd /S /C on Windows)
RUN ["<executable>", "<param1>", "<param2>"] (exec form)
```

Information:
- The exec form makes it possible to avoid shell string munging, and to RUN commands using a base image that does not contain the specified shell executable.
- The default shell for the shell form can be changed using the SHELL command.
- Normal shell processing does not occur when using the exec form. For example, RUN ["echo", "$HOME"] will not do variable substitution on $HOME.


## CMD
Usage:
```
CMD ["<executable>","<param1>","<param2>"] (exec form, this is the preferred form)
CMD ["<param1>","<param2>"] (as default parameters to ENTRYPOINT)
CMD <command> <param1> <param2> (shell form)
```
Information:
- The main purpose of a CMD is to provide defaults for an executing container. These defaults can include an executable, or they can omit the executable, in which case you must specify an ENTRYPOINT instruction as well.
- There can only be one CMD instruction in a Dockerfile. If you list more than one CMD then only the last CMD will take effect.
- If CMD is used to provide default arguments for the ENTRYPOINT instruction, both the CMD and ENTRYPOINT instructions should be specified with the JSON array format.
- If the user specifies arguments to docker run then they will override the default specified in CMD.
- Normal shell processing does not occur when using the exec form. For example, CMD ["echo", "$HOME"] will not do variable substitution on $HOME.

## LABEL
Usage:
```
LABEL <key>=<value> [<key>=<value> ...]
```

Information:
- The LABEL instruction adds metadata to an image.
- To include spaces within a LABEL value, use quotes and backslashes as you would in command-line parsing.
- Labels are additive including LABELs in FROM images.
- If Docker encounters a label/key that already exists, the new value overrides any previous labels with identical keys.
- To view an image’s labels, use the docker inspect command. They will be under the "Labels" JSON attribute.

## EXPOSE
Usage:
```
EXPOSE <port> [<port> ...]
```
Information:
- Informs Docker that the container listens on the specified network port(s) at runtime.
- EXPOSE does not make the ports of the container accessible to the host.

## ENV
Usage:
```
ENV <key> <value>
ENV <key>=<value> [<key>=<value> ...]
```
Information:
- The ENV instruction sets the environment variable <key> to the value <value>.
- The value will be in the environment of all “descendant” Dockerfile commands and can be replaced inline as well.
- The environment variables set using ENV will persist when a container is run from the resulting image.
- The first form will set a single variable to a value with the entire string after the first space being treated as the <value> - including characters such as spaces and quotes.


## ADD
Usage:
```
ADD <src> [<src> ...] <dest>
ADD ["<src>", ... "<dest>"] (this form is required for paths containing whitespace)
```
Information:
- Copies new files, directories, or remote file URLs from <src> and adds them to the filesystem of the image at the path <dest>.
<src> may contain wildcards and matching will be done using Go’s filepath.Match rules.
- If <src> is a file or directory, then they must be relative to the source directory that is being built (the context of the build).
<dest> is an absolute path, or a path relative to WORKDIR.
- If <dest> doesn’t exist, it is created along with all missing directories in its path.

## COPY
Usage:
```
COPY <src> [<src> ...] <dest>
COPY ["<src>", ... "<dest>"] (this form is required for paths containing whitespace)
```
Information:
- Copies new files or directories from <src> and adds them to the filesystem of the image at the path <dest>.
- <src> may contain wildcards and matching will be done using Go’s filepath.Match rules.
- <src> must be relative to the source directory that is being built (the context of the build).
- <dest> is an absolute path, or a path relative to WORKDIR.
- If <dest> doesn’t exist, it is created along with all missing directories in its path.


## ENTRYPOINT
Usage:
```
ENTRYPOINT ["<executable>", "<param1>", "<param2>"] (exec form, preferred)
ENTRYPOINT <command> <param1> <param2> (shell form)
```
Information:
- Allows you to configure a container that will run as an executable.
- Command line arguments to docker run <image> will be appended after all elements in an exec form ENTRYPOINT and will override all elements specified using CMD.
- The shell form prevents any CMD or run command line arguments from being used, but the ENTRYPOINT will start via the shell. This means the executable will not be PID 1 nor will it receive UNIX signals. Prepend exec to get around this drawback.
- Only the last ENTRYPOINT instruction in the Dockerfile will have an effect.

## VOLUME
Usage:
```
VOLUME ["<path>", ...]
VOLUME <path> [<path> ...]
```
Creates a mount point with the specified name and marks it as holding externally mounted volumes from native host or other containers.


## USER
Usage:
```
USER <username | UID>
```
The USER instruction sets the user name or UID to use when running the image and for any RUN, CMD and ENTRYPOINT instructions that follow it in the Dockerfile.


## WORKDIR
Usage:
```
WORKDIR </path/to/workdir>
```
Information:
- Sets the working directory for any RUN, CMD, ENTRYPOINT, COPY, and ADD instructions that follow it.
- It can be used multiple times in the one Dockerfile. If a relative path is provided, it will be relative to the path of the previous WORKDIR instruction.

## ARG
Usage:
```
ARG <name>[=<default value>]
```
Information:
- Defines a variable that users can pass at build-time to the builder with the docker build command using the --build-arg <varname>=<value> flag.
- Multiple variables may be defined by specifying ARG multiple times.
- It is not recommended to use build-time variables for passing secrets like github keys, user credentials, etc. Build-time variable values are visible to any user of the image with the docker history command.
- Environment variables defined using the ENV instruction always override an ARG instruction of the same name.
- Docker has a set of predefined ARG variables that you can use without a corresponding ARG instruction in the Dockerfile.
  - HTTP_PROXY and http_proxy
  - HTTPS_PROXY and https_proxy
  - FTP_PROXY and ftp_proxy
  - NO_PROXY and no_proxy


## ONBUILD
Usage:
```
ONBUILD <Dockerfile INSTRUCTION>
```
Information:
- Adds to the image a trigger instruction to be executed at a later time, when the image is used as the base for another build. The trigger will be executed in the context of the downstream build, as if it had been inserted immediately after the FROM instruction in the downstream Dockerfile.
- Any build instruction can be registered as a trigger.
- Triggers are inherited by the "child" build only. In other words, they are not inherited by "grand-children" builds.
- The ONBUILD instruction may not trigger FROM, MAINTAINER, or ONBUILD instructions.


## STOPSIGNAL
Usage:
```
STOPSIGNAL <signal>
```

The STOPSIGNAL instruction sets the system call signal that will be sent to the container to exit. This signal can be a valid unsigned number that matches a position in the kernel’s syscall table, for instance 9, or a signal name in the format SIGNAME, for instance SIGKILL.

## HEALTHCHECK
Usage:
```
HEALTHCHECK [<options>] CMD <command> (check container health by running a command inside the container)
HEALTHCHECK NONE (disable any healthcheck inherited from the base image)
```

Information:
- Tells Docker how to test a container to check that it is still working
- Whenever a health check passes, it becomes healthy. After a certain number of consecutive failures, it becomes unhealthy.
- The <options> that can appear are…
  - --interval=<duration> (default: 30s)
  - --timeout=<duration> (default: 30s)
  - --retries=<number> (default: 3)
- The health check will first run interval seconds after the container is started, and then again interval seconds after each previous check completes. If a single run of the check takes longer than timeout seconds then the check is considered to have failed. It takes retries consecutive failures of the health check for the container to be considered unhealthy.
- There can only be one HEALTHCHECK instruction in a Dockerfile. If you list more than one then only the last HEALTHCHECK will take effect.
<command> can be either a shell command or an exec JSON array.
- The command's exit status indicates the health status of the container.
  - 0: success - the container is healthy and ready for use
  - 1: unhealthy - the container is not working correctly
  - 2: reserved - do not use this exit code
- The first 4096 bytes of stdout and stderr from the <command> are stored and can be queried with docker inspect.
- When the health status of a container changes, a health_status event is generated with the new status.


## SHELL
Usage:
```
SHELL ["<executable>", "<param1>", "<param2>"]
```
Information:
- Allows the default shell used for the shell form of commands to be overridden.
- Each SHELL instruction overrides all previous SHELL instructions, and affects all subsequent instructions.
- Allows an alternate shell be used such as zsh, csh, tcsh, powershell, and others.





