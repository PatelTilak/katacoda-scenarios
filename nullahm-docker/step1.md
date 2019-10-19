
### List existing Images

`docker image ls`{{copy}}

### Download new Images

Lets download hello-world Images

`docker pull hello-world`{{copy}}

Verify that image is available is images list

`docker image ls`{{copy}}

### Update existing Images

Updating is same as downloading new one.

Ubuntu image is already present in our images list but seems outdated.

Lets download the latest version.

`docker pull ubuntu`{{copy}} 

### Download older Image

You can check available versions of Image on Docker Hub page for respective image

For ubuntu check https://hub.docker.com/_/ubuntu

Lets download Ubuntu 16.04 - Xenial

`docker pull ubuntu:xenial`{{copy}} 

Verify if newly download old image is available is images list

`docker image ls`{{copy}}

### This completes Step 1