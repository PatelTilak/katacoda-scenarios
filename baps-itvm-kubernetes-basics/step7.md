### Self-Healing Demo

Now for something interesting. Instead of deleting the Pod, lets stop the nginx process **inside** the container and see how Kubernetes reacts.

First, open a second terminal and watch the Pods continuously

`kubectl get pods -w`{{copy}}

Now in this terminal, stop nginx inside the running Pod

`kubectl exec <pod-name> -- nginx -s stop`{{copy}}

Watch the second terminal. You will see the Pod status change briefly and the **RESTARTS** counter go up. Kubernetes detected the container failure and restarted it automatically.

### Confirm the Restart

Check logs again — they will show nginx starting fresh, confirming the container was restarted

`kubectl logs <pod-name>`{{copy}}

Now describe the Pod again

`kubectl describe pod <pod-name>`{{copy}}

Look at two things:
- **Restart Count** — now shows 1
- **Events** — shows the container was killed and started again

This is **self-healing**. Kubernetes ensures your application stays running even when the process inside crashes.

### What about deleting the Pod itself?

We saw Kubernetes restart a crashed container. What if someone deletes the entire Pod?

`kubectl delete pod <pod-name>`{{copy}}

List Pods immediately

`kubectl get pods`{{copy}}

A brand new Pod was created with a new name. The Deployment noticed one Pod was missing and replaced it. There is no way to permanently remove a Pod managed by a Deployment — unless you delete the Deployment itself.

### This completes Step 7
