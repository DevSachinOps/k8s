# Deployments


### Create a deployment
`kubectl create deployment --image=nginx nginx`

### Create deployment definition file and don't create
`kubectl create deployment --image=nginx nginx --dry-run=client -o yaml`

### Generate the file and don't create the deployment
`kubectl create deployment --image=nginx nginx --dry-run=client -o yaml > nginx-deploy.yml`

Save it to a file, make necessary changes to the file (for example, adding more replicas) and then create the deployment.
