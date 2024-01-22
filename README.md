# kubernetesGo
Learning to Program Kubernetenes with Go.

## Creating a cluster 
To create a cluster begin by using the following command
```bash
kind create cluster --config Cluster/config.yaml
```
This will create the cluster with 3 worker node.

## API Proxy
Inorder to connect with the kubernetes API directly we can use the kube proxy to open a route

```bash
kubectl proxy --port=8080
```
This following command creates a proxy server or application-level gateway between localhost and the Kubernetes API server.[Proxy doc](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#proxy)
 

 ## Connect to API
 Once the proxy is setup a Http connection can be made at the proxy port which in this case is 8080

 ```bash
 curl -v http://localhost:8080/api
 ```
