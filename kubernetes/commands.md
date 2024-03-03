
> kubectl version

> kubectl --help

> kubectl get all

> kubectl get nodes

> kubectl get nodes -o wide

> kubectl create -f pod-defn.yaml

> kubectl apply -f pod-defn.yaml

> kubectl get pods

> kubectl describe pod pod-name

> kubectl run pod-name --image=image-name

> kubectl delete pod pod-name

> kubectl run redis --image=redis123 --dry-run=client -o yaml > redis-definition.yaml

> kubectl replace -f rs-defn.yaml

> kubectl scale --replicas=6 rs-defn.yaml

> kubectl scale --replicas=6 replicaset rs-name

> kubectl get replicaset

> kubectl delete replicaset rs-name

> kubectl describe replicaset

