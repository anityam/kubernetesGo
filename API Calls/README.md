# API Calls
We can examine various kubernetes api based call using the curl with the proxy setup in [top level readme](./README.md).

## Env variables
To make it easier for typing we will set the env variable for the localhost to HOST variable

```bash
HOST=http://localhost:8080  # Inorder for this to work the kube proxy needs to be setup to work on 8080
```
For persistance this can be set in `.zshrc` or `bashrc`

## Examine a call
The defacto tool for interacting with a Kubernetes cluster is `kubectl`. For each call made with the kubectl we can identify the API endpoints or display the endpoints by adding a verbosity level to the running `kubectl` command.

```bash
kubectl get po -v6 
...
round_trippers.go:553] GET https://127.0.0.1:50107/api/v1/namespaces/default/pods?limit=500 200 OK in 3 milliseconds
```
`v6` only displays the method header and request timing. In oder to get the response body use the `-v8` 

```bash
kubectl get pods -v8
...
Response Body: {"kind":"Table","apiVersion":"meta.k8s.io/v1","metadata":{"resourceVersion":"9224"},"columnDefinitions":[{"name":"Name","type":"string","format":"name","description":"Name must be unique within a namespace. Is required when creating resources, although some resources may allow a client to request the generation of an appropriate name automatically. Name is primarily intended for creation idempotence and configuration definition. Cannot be updated. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names#names","priority":0},{"name":"Ready","type":"string","format":"","description":"The aggregate readiness state of this pod for accepting traffic.","priority":0},{"name":"Status","type":"string","format":"","description":"The aggregate status of the containers in this pod.","priority":0},{"name":"Restarts","type":"string","format":"","description":"The number of times the containers in this pod have been restarted and when the last container in this pod has restarted.","priority":0},{"n [truncated 1932 chars]
```

> On the above calls some outputs have been removed to keep the README short.


