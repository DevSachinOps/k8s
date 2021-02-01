### Replicaset
Replicaset consider the pods which are already running and not the part of the replicaset but matching the selector.

The above one is main difference in replicaset and replication controller.

#### Create Replicaset
* Create replicaset with file `kubectl create -f replicaset.yml`

OR

* `kubectl apply -f replicaset.yml`


#### Scale Replicaset
* Update the `.yml` file with `replicas: 6` and run the command `kubectl replace -f replicaset.yml`

* `kubectl scale --replicas=6 -f replicaset.yml`

* `kubectl scale --replicas=6 replicaset replicaset-name` But this method will not update the defintion file. Current replica set will be updated with 6 replicas but defintion file will still be having 3 replicas.
