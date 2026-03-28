### Scale a Deployment

One of the most powerful features of Kubernetes is the ability to scale applications up or down with a single command.

Check the current state of our Deployment

`kubectl get deployment nginx`{{copy}}

Currently we have 1 replica. Lets scale it up to 5

`kubectl scale deployment nginx --replicas=5`{{copy}}

Watch the new Pods come up

`kubectl get pods`{{copy}}

Run it a few times to see all 5 Pods reach the `Running` state.

All 5 Pods are served by the same Service we created in the previous step — requests are automatically load balanced across them.

### Scale Down

Lets scale back down to 2 replicas

`kubectl scale deployment nginx --replicas=2`{{copy}}

`kubectl get pods`{{copy}}

Kubernetes terminates the extra Pods gracefully.

### Update the Application Image

Lets update nginx to a specific version

`kubectl set image deployment/nginx nginx=nginx:1.25`{{copy}}

Watch the rolling update happen

`kubectl rollout status deployment/nginx`{{copy}}

Kubernetes replaces Pods one by one so the application stays available during the update.

### Rollback

If something goes wrong you can rollback to the previous version

`kubectl rollout undo deployment/nginx`{{copy}}

`kubectl rollout status deployment/nginx`{{copy}}

### Cleanup

`kubectl delete service nginx`{{copy}}

`kubectl delete deployment nginx`{{copy}}

### This completes Step 5
