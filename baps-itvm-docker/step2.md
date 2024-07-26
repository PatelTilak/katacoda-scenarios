### Spawn the hello-world Container

`docker run hello-world`{{copy}}

Congratulations!! You just spawned & ran your first container.

### List existing Containers

`docker container ls`{{copy}}

We are not able to see any Containers here because by default it will show only running containers.

Our hello-world container has already finished its work & stopped.

To view stopped containers as well, pass -a argument 

`docker container ls -a`{{copy}}

Same can be done by using shorthand command as well

`docker ps -a`{{copy}}

## Remove Container

To remove container we can use `docker container rm <containerName_OR_containerId>` command

For example, if container name is `abc` you can remove it using `docker container rm abc`

You can view Container Name or ID by listing existing containers. Recall commands from previous Step & remove the `hello-world` container created in this step.

Explore other docker commands by using inbuilt help provided by command 

`docker --help`{{copy}}

### This completes Step 2