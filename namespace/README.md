# Namespace

### Specifying the resources in a particular namespace

#### While running the commands
`kubectl run nginx --image=nginx --namespace=development`

`kubectl get pods --namespace=development`

#### In side the Definition file, we can specify under metadata section.
```
metadata:
  name: mypod
  namespace: development
```

### Set the default Namespace
`kubectl config set-context $(kubectl config current-context) --namespace=dev`

### Get resources of all namespaces
`kubectl get pods --all-namespaces`

### Access service in same namespace
`db-service`
This will be just the service name. We can directly use the service name within the namespace.

### Access service in different namespace
![image](https://user-images.githubusercontent.com/33462331/111021108-27ea7a80-83f0-11eb-8f89-87c8375c46a2.png)
