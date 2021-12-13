# Kubernetes
Automation deployment, scaling, and container manager or orchestration.

## Node
`kubectl get node`
`kubectl describe node [node-name]`


## Pod
`kubectl get pod`
`kubectl describe pod [pod-name]`

### Pod:Create
`kubectl create -f [file.yaml]`
`kubectl create -f examples/pod-nginx.yaml`

### Pod:Delete
`kubectl delete pod [name]`
`kubectl delete pod [name1] [name2] [name3] ...`

### Pod:Label
`kubectl get pods --show-labels`
`kubectl label pod namapod key=value`
`kubectl label pod namapod key=value --overwrite`
`kubectl get pods -l key`
`kubectl get pods -l key=value`
`kubectl get pods -l '!key'`
`kubectl get pods -l key!=value`
`kubectl get pods -l 'key in (value1,value2)'`
`kubectl get pods -l 'key notin (value1,value2)'`
`kubectl get pods key,key2=value`
`kubectl get pods key=value,key2=value`

### Pod:Label delete pod
`kubectl delete pod -l key=value`
`kubectl delete pod --all --namespace [name]`

### Pod:Annotation
`kubectl annotate pod namapod key=value`
`kubectl annotate pod namapod key=value --overwrite`


## Pod Port Forward
`kubectl port-forward [pod-name] [external-port]:[inner-port]`


## Namespace
`kubectl get namespaces`
`kubectl get namespace`
`kubectl get ns`
`kubectl get pod --namespace [name]`
`kubectl get pod -n [name]`

### Namespace:Create
`kubectl create -f [file.yaml]`
`kubectl create -f examples/namespace-finance.yaml`

## Namespace:Create pod based namespace
`kubectl create -f [file.yaml] --namespace [name]`
`kubectl create -f examples/pod-nginx.yaml --namespace [name]`

### Namespace:Delete
`kubectl delete namespace [name]`


## Probe
Liveness, Readiness and Startup
- HTTP Get
- TCP Socket
- Command Exec
`kubectl get pod`
`kubectl describe pod [name]`


## Replication Controller
`kubectl get replicationcontrollers`
`kubectl get rc`

### Replication Controller:Create
`kubectl create -f [name.yaml]`
`kubectl create -f examples/replication-controller-nginx.yaml`

### Replication Controller:Delete
`kubect delete replicationcontrollers [name]`
`kubect delete rc [name]`

Delete without remove pods inside label
`kubect delete replicationcontrollers [name] --cascade=orphan`


## Replica Set (Improvement of Replication Controller)
`kubectl get replicasets`
`kubectl get rc`

### Replica Set:Create
`kubectl create -f [name.yaml]`
`kubectl create -f examples/replica-set-nginx.yaml`

### Replication Controller:Delete
`kubect delete replicasets [name]`
`kubect delete rs [name]`
