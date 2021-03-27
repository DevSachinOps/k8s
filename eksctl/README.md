# eksctl commands

`eksctl create cluster`

`eksctl create cluster -f cluster.yaml`

`eksctl delete cluster -f cluster.yaml`

`eksctl update cluster -f cluster.yaml --approve`

#### nodegroup

`eksctl create nodegroup --config-file=cluster.yaml`

`eksctl create nodegroup --config-file=cluster.yaml --include='ng-2'`. This way we can specify to create a specific node group from the configurations file.

`eksctl delete nodegroup --cluster=cluster-name --name=ng-1 --approve`

`eksctl delete nodegroup -f --config-file=cluster.yaml --include="ng-1" --approve`

#### Scale the node group

`eksctl scale nodegroup --cluster=EKS-course-cluster --nodes=5 --name=scale-spot`. This will scale node group to 5.


Deploy this deployment
```
https://raw.githubusercontent.com/kubernetes/autoscaler/master/cluster-autoscaler/cloudprovider/aws/examples/cluster-autoscaler-autodiscover.yaml
```

Then edit the deployment with our cluster name and version of image as per your cluster's version

``` 
- --node-group-auto-discovery=asg:tag=k8s.io/cluster-autoscaler/enabled,k8s.io/cluster-autoscaler/EKS-course-cluster
image: k8s.gcr.io/autoscaling/cluster-autoscaler:v1.18.3
 ```

Deploy an  test application with scheduling on the specific node.

For example taking `nginx-deployment.yml` and using nodeAffinity for the same.

`kubectl scale --replicas=5 deployment test-autoscaler` Initially some pods will be coming as pending, then ASG will get scaled and launch new instances and pods will get scheduled on the newly launched nodes.














