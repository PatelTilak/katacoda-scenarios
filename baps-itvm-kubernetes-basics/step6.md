### Export Resources as YAML

Everything in Kubernetes can be expressed as YAML. You can export any running resource to see its full definition — useful for saving configs, version-controlling them, or reapplying them on another cluster.

### Export the Deployment

`kubectl get deployment nginx -o yaml`{{copy}}

This prints the full YAML definition of the Deployment. Notice it includes fields like `status` and `resourceVersion` that are added by Kubernetes at runtime.

To save it to a file

`kubectl get deployment nginx -o yaml > nginx-deployment.yaml`{{copy}}

`cat nginx-deployment.yaml`{{copy}}

### Export the Service

`kubectl get service nginx -o yaml`{{copy}}

Save it to a file

`kubectl get service nginx -o yaml > nginx-service.yaml`{{copy}}

`cat nginx-service.yaml`{{copy}}

### Combined Export

Instead of two separate files, you can export both resources together in a single YAML file separated by `---`

`kubectl get deployment,service nginx -o yaml > nginx.yaml`{{copy}}

`cat nginx.yaml`{{copy}}

The combined file has both resources in sequence. You can apply the entire file at once on any cluster

`kubectl apply -f nginx.yaml`{{copy}}

This is how teams store their application definitions in source control and redeploy them consistently across environments.

### This completes Step 6
