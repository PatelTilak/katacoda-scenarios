### Spawn container with Restricted memory

We can see the resource usage of containers using

`docker stats`{{copy}}

Press Ctrl + C to exit

By default there are no restrictions on Resource usage. But we can limit Memory or any other resource for individual containers.

Lets spawn container with 1 GB Memory

`docker run --name nginx6 -p 80:80 -v "$PWD"/html:/usr/share/nginx/html:ro -d -m 1g nginx`{{copy}}

Check the resources containers using

`docker stats`{{copy}}

Notice the available memory of nginx6 container


Now Lets clear all the Mess we have created

`docker container stop nginx1`{{copy}}
`docker container stop nginx2`{{copy}}

Instead of doing this for all, lets do some smart work

`docker stop $(docker ps -a -q)`{{copy}}

This will stop all the containers

To remove all stopped containers, you can use

`docker container prune`{{copy}}

### This completes Step 3