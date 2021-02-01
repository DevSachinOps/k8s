### Replicaset

* Create replicaset with file `kubectl create -f replicaset.yml`
* Replicaset consider the pods which are already running and not the part of the replicaset but matching the selector.
* The above one is main difference in replicaset and replication controller.