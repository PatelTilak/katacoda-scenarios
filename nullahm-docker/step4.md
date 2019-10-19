### Run nginx server using Docker

Now Lets host a static website on nginx which is running as Docker container

Before we spawn nginx container, lets create static page which will be served by nginx.

Create Directory named `html`

`mkdir html`{{copy}}

Create `index.html` in `html` directory

`echo "<h1>Null Ahmedabad Rocks</h1>" >> ./html/index.html`{{copy}}

Verify that file is written properly

`cat ./html/index.html`{{copy}}

Now that we have static website ready, Lets spawn nginx container

`docker run --name nginx -p 80:80 -v "$PWD"/html:/usr/share/nginx/html:ro nginx`{{copy}}

Understanding the command:
--name specifies the name of created container
-p <Host_Port>:<Container_Port> Maps Container's Port Container_Port with Host's Port Host_Port
-v <Host_Directory>:<Container_Directory>:<CommaSeperated_Options> Maps Container's Directory (Volume) Container_Directory with Host's Directory Host_Directory. ro in CommaSeperated_Options indicated that the volume shoud be mounted as Read-Only volume


View the Webpage at: 
<pre>https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com</pre>

Lets stop the Container & Remove it

`docker container stop nginx`{{copy}}

`docker container rm nginx`{{copy}}

Now Lets create new nginx container which is accesible via port 8080 of host

`docker run --name nginx -p 8080:80 -v "$PWD"/html:/usr/share/nginx/html:ro nginx`{{copy}}

View the Webpage at: 
<pre>https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com</pre>

Lets stop the Container & Remove it

`docker container stop nginx`{{copy}}

`docker container rm nginx`{{copy}}

To run Container in Console detached, we can use -d Parameter (ie. will run in background)

To Instruct docker to automatically remove container when it is stopped, we can use --rm Parameter

Lets Spawn container using above two arguments

`docker run --name nginx -p 80:80 -v "$PWD"/html:/usr/share/nginx/html:ro --rm -d nginx`{{copy}}

View the Webpage at: 
<pre>https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com</pre>

Lets stop the Container

`docker container stop nginx`{{copy}}

Verify if it is removed automatically

`docker ps -a | grep nginx`{{copy}}

### Run multiple nginx servers using Docker

Lets start multiple nginx servers using different ports

`docker run --name nginx1 -p 8081:80 -v "$PWD"/html:/usr/share/nginx/html:ro nginx`{{copy}}

`docker run --name nginx2 -p 8082:80 -v "$PWD"/html:/usr/share/nginx/html:ro nginx`{{copy}}

`docker run --name nginx3 -p 8083:80 -v "$PWD"/html:/usr/share/nginx/html:ro nginx`{{copy}}

`docker run --name nginx4 -p 8084:80 -v "$PWD"/html:/usr/share/nginx/html:ro nginx`{{copy}}

`docker run --name nginx5 -p 8085:80 -v "$PWD"/html:/usr/share/nginx/html:ro nginx`{{copy}}

View the Webpages at: 
<pre>https://[[HOST_SUBDOMAIN]]-8081-[[KATACODA_HOST]].environments.katacoda.com</pre>
<pre>https://[[HOST_SUBDOMAIN]]-8082-[[KATACODA_HOST]].environments.katacoda.com</pre>
<pre>https://[[HOST_SUBDOMAIN]]-8083-[[KATACODA_HOST]].environments.katacoda.com</pre>
<pre>https://[[HOST_SUBDOMAIN]]-8084-[[KATACODA_HOST]].environments.katacoda.com</pre>
<pre>https://[[HOST_SUBDOMAIN]]-8085-[[KATACODA_HOST]].environments.katacoda.com</pre>

Was it Hard ?? Imagine the efforts you will have to put if you had to do it without Docker...

### This completes Step 4

