### Explore the Cluster

Kubernetes is a container orchestration platform. It manages containers across multiple machines called **Nodes**.

Lets check if our cluster is ready

`kubectl cluster-info`{{copy}}

### View Nodes

A Kubernetes cluster has one or more Nodes. Lets list them

`kubectl get nodes`{{copy}}

To see more details about the nodes

`kubectl get nodes -o wide`{{copy}}

### View all running components

Kubernetes itself runs as containers inside the cluster. Lets see them

`kubectl get pods --all-namespaces`{{copy}}

You will notice pods running in the `kube-system` namespace — these are the core Kubernetes components like the API server, scheduler, and DNS.

### Key Concepts

**Pod** — smallest deployable unit, wraps one or more containers

**Node** — a machine (VM or physical) that runs Pods

**Namespace** — a way to group and isolate resources within the same cluster

Lets list the default namespaces

`kubectl get namespaces`{{copy}}

### This completes Step 1
