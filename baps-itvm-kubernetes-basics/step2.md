### Run your First Pod

The simplest way to run a container in Kubernetes is to create a Pod directly.

Lets run an nginx Pod

`kubectl run nginx --image=nginx`{{copy}}

List all Pods to see it

`kubectl get pods`{{copy}}

The Pod may show `ContainerCreating` initially while the image is being pulled. Run the command again until it shows `Running`

`kubectl get pods`{{copy}}

### Describe a Pod

`kubectl describe pod nginx`{{copy}}

Notice the **Events** section at the bottom — it shows the lifecycle of the Pod (Scheduled → Pulling → Running).

### View Pod Logs

`kubectl logs nginx`{{copy}}

### Run a Command inside the Pod

Lets open an interactive shell inside the running nginx Pod

`kubectl exec -it nginx -- /bin/bash`{{copy}}

Verify nginx is running inside the container

`curl localhost`{{copy}}

Exit the container

`exit`{{copy}}

### Delete the Pod

`kubectl delete pod nginx`{{copy}}

Verify it is gone

`kubectl get pods`{{copy}}

### This completes Step 2
