### Interact with container

Lets spawn Alpine Linux Container

`docker run alpine`{{copy}}

Container just exited without doing anything.

Lets use Interactive shell to interact with the container. -it instructs docker to start new interactive terminal

`docker run -it alpine`{{copy}}

Now we are inside Alpine Linux container.

We can verify this by checking os-release

`cat /etc/os-release `{{copy}}

Now exit the container

`exit`{{copy}}

Check `/etc/os-release` again

`cat /etc/os-release `{{copy}}

Noticed the difference ? Now it is showing as Ubuntu which is our host os.

Lets try to read os-release from centos image as well

`docker run centos cat /etc/os-release`{{copy}}

Notice that we are not requesting Interactive shell here as we just want to execute one command. It can be directly provided as commandline parameter

Try the same approach with ubuntu & alpine images as well.

### This completes Step 3