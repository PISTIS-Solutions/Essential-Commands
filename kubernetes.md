# Kubernetes Commands and Their Usage
## Basic Commands

Create a Resource

```sh
kubectl create -f <filename>
```
Create a resource from a file or from stdin.

### Apply a Configuration

```sh
kubectl apply -f <filename>
```
Apply a configuration to a resource by file name or stdin.

### Delete Resources
```sh
kubectl delete -f <filename>
```
Delete resources by file names, stdin, resources and names, or by resources and label selector.

### Get Commands
Get Pods
```sh
kubectl get pods
```
List all pods in the namespace.

### Get Services
```sh
kubectl get svc
```
List all services in the namespace.

### Get Nodes
```sh
kubectl get nodes
```
List all nodes in the cluster.

### Get Deployments
```sh
kubectl get deployments
```
List all deployments in the namespace.

### Describe Commands
Describe Pod
```sh

kubectl describe pod <pod_name>
```
Show detailed information about a pod.

### Describe Service
```sh
kubectl describe svc <service_name>
```
Show detailed information about a service.

### Describe Node
```sh
kubectl describe node <node_name>
```
Show detailed information about a node.

### Describe Deployment
```sh
kubectl describe deployment <deployment_name>
```
Show detailed information about a deployment.

### Logs Commands
Get Pod Logs
```sh
kubectl logs <pod_name>
```
Print the logs for a container in a pod.

### Get Specific Container Logs
```sh
kubectl logs <pod_name> -c <container_name>
```
Print the logs for a specific container in a pod.

### Execute Commands
Execute a Command in a Container
```sh

kubectl exec <pod_name> -- <command>
```
Execute a command in a container.

### Execute an Interactive Shell in a Container
```sh
kubectl exec -it <pod_name> -- /bin/bash
```
Start a bash session in a container.

### Port Forwarding
Forward a Port to a Pod
```sh
kubectl port-forward <pod_name> 
<local_port>:<pod_port>
```
Forward one or more local ports to a pod.

### Scale a Deployment
```sh
kubectl scale --replicas=<number> deployment/<deployment_name>
```
Set the number of replicas for a deployment.

### Edit Resources
Edit a Resource
```sh
kubectl edit <resource_type>/<resource_name>
```
Edit a resource on the server.

### Apply a Configuration Change
```sh
kubectl rollout restart deployment/<deployment_name>
```
### Restart a deployment.

Roll Back to a Previous Deployment Revision
```sh
kubectl rollout undo deployment/<deployment_name>
```
Roll back to a previous deployment revision.

### Namespace Management
List Namespaces
```sh
kubectl get namespaces
```
List all namespaces.

### Create a Namespace
```sh
kubectl create namespace <namespace_name>
```
Create a new namespace.

### Delete a Namespace
```sh
kubectl delete namespace <namespace_name>
```
Delete a namespace.

### Configuration
View the Current Context
```sh

kubectl config current-context
```
Display the current-context.

### Set the Current Namespace
``` sh

kubectl config set-context --current --namespace=<namespace>
```
Set the default namespace for the current context.

### Secrets and ConfigMaps
Create a Secret from Literal Values
```sh
kubectl create secret generic <secret_name> --from-literal=<key>=<value>
```
Create a secret from literal values.

### Create a ConfigMap from Literal Values
```sh
kubectl create configmap <configmap_name> --from-literal=<key>=<value>
```
Create a ConfigMap from literal values.

### Get Secrets
```sh
kubectl get secrets
```
List all secrets.

### Get ConfigMaps
```sh
kubectl get configmaps
```
List all ConfigMaps.

### Events
View Events
```sh
kubectl get events
```
List events.

## Troubleshooting Commands
Show Cluster Info
```sh

kubectl cluster-info
```
Display cluster info.

### Run Diagnostic
``` sh
kubectl run -i --tty busybox --image=busybox -- sh
```
Run an interactive shell in a pod for diagnostic purposes.

### Explain Resource
```sh
kubectl explain <resource>
```
Get documentation for a resource.

## Additional Commands
### Autoscale a Deployment
```sh
kubectl autoscale deployment <deployment_name> --min=<min> --max=<max> --cpu-percent=<percentage>
```
Autoscale a deployment.

### Attach to a Running Container
```sh
kubectl attach <pod_name> -c <container_name>
```
Attach to a running container.

### Copy Files to and from Containers
```sh
kubectl cp <file_path> <pod_name>:/<container_path>
```
### Copy files to a container.

```sh
kubectl cp <pod_name>:/<container_path> <file_path>
```
Copy files from a container.

### Label a Resource
```sh
kubectl label <resource_type> <resource_name> <label_key>=<label_value>
```
Add or update a label on a resource.

### Annotate a Resource
``` sh
kubectl annotate <resource_type> <resource_name> <annotation_key>=<annotation_value>
```
Add or update an annotation on a resource.

### Top Commands
Get CPU and Memory Usage for Nodes
``` sh

kubectl top nodes
```
Show metrics for nodes.

Get CPU and Memory Usage for Pods
```sh

kubectl top pods
```
Show metrics for pods.