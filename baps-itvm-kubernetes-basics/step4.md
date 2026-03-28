### Expose the Application with a Service

Pods get a new IP address every time they restart. A **Service** gives a stable endpoint to reach Pods regardless of restarts.

Lets expose the nginx Deployment on port 80

`kubectl expose deployment nginx --port=80 --type=NodePort`{{copy}}

List Services

`kubectl get services`{{copy}}

Notice the `PORT(S)` column shows something like `80:3XXXX/TCP`. The second port (NodePort) is the port on the Node you can use to access the app.

### Access the Application

Get the NodePort assigned

`kubectl get service nginx`{{copy}}

Note the NodePort value and access the nginx page at:

{{TRAFFIC_HOST1_PORT}}

You should see the nginx welcome page.

### ClusterIP vs NodePort vs LoadBalancer

**ClusterIP** — accessible only within the cluster (default)

**NodePort** — accessible from outside the cluster via a port on the Node

**LoadBalancer** — provisions a cloud load balancer (used in managed cloud Kubernetes)

### This completes Step 4
