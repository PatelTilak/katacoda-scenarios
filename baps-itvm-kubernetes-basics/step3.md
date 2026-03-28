### Deploy an Application

In production, we don't manage Pods directly. We use a **Deployment** which ensures the desired number of Pod replicas are always running.

Lets create an nginx Deployment

`kubectl create deployment nginx --image=nginx`{{copy}}

List the Pods created by the Deployment

`kubectl get pods`{{copy}}

Notice the Pod name has a random suffix — this is managed by the Deployment.

### Inspect the Pod

`describe` gives detailed information about a resource — status, container details, and most importantly the **Events** section which shows exactly what Kubernetes did.

Replace `<pod-name>` with the name from the previous command

`kubectl describe pod <pod-name>`{{copy}}

Scroll to the **Events** section at the bottom. You can see the full lifecycle: Scheduled → Pulling → Pulled → Created → Started.

### View Logs

Logs let us see what is happening inside the container

`kubectl logs <pod-name>`{{copy}}

### This completes Step 3
