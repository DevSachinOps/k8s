# Deployments


### Create a deployment
`kubectl create deployment --image=nginx nginx`

### Create deployment definition file and don't create
`kubectl create deployment --image=nginx nginx --dry-run=client -o yaml`

### Generate the file and don't create the deployment
`kubectl create deployment --image=nginx nginx --dry-run=client -o yaml > nginx-deploy.yml`

Save it to a file, make necessary changes to the file (for example, adding more replicas) and then create the deployment.

### Scale the deployment
`kubectl scale deployment --replicas=6 nginx`

### Get Deployments list
`kubectl get deployments`

`kubectl get deploy`


### Get specific deployment 
`kubectl get deployment deployment-name`

### Get details of deployment
`kubectl describe deployment deployment-name`
