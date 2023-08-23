  # what is Kubernets
   - it is container orchestraton tool
   - help to manage containerized applicatins in different deploment enviroment (cloud, on premise)
# What problem does K8s solve
 - trend from Monolith to microservice
 - increased usage of contianers
 - if u have alot of container , the effort to write script to just maintain and make it avalible at anytime would be hard
 - demand for a `proper way ` of `managing ` contianers
# what  orchestraion do?
 - high availability
 - scalbility
 - disaster recovery
# kubernets architecture
 - one main,master Node, most importance node
 - and alot of worker node
 - weach node have one or more container in them
# main Node
 - Api server= entrypoint to K8s cluster
 - Controller Manger= keep track of whats happing in the cluster
 - schduler= ensures pods placement
 - etcd: backing store
 - can have multiple main node if needed
# node and pod
 node is the pyshicall layer, pod is the smallest unit in k8s, an outer layer over container, best pratice is 1 application per pod

  - each pod have a ip address, but it change once the pod restar
  - pod connect with each orther by ip
# Service and ingress
 - service is permanat ip address
 - lifecycle of pod and service connected
 - we can have internal serive or external service
 - Ingress in Kubernetes is an API object that manages external access to the services in a cluster, typically HTTP and HTTPS. Ingress can provide load balancing, SSL termination, and name-based virtual hosting.

 - ingress like a security group
# configmap and secret
 - what happen if u just need to change like the api or something normaly u can use (env) in k8s we call it configmaps
 - but some time we need more than plain text: we can use secret
# volume 
 connect external data file that every pod can use
  - key k8s doesnt manage data presustance
# Deplpyment and statefulset
- if a pod die, we can replicate everything on k8s so that it will have the same permanet ip, load balancerm, scailing group
- service also a load ballcer
- for repliaction, define bluement for pods (a deployments)
- deploments abstract of pod, pod abstract of container
- but for db it need another database to hold the current state of the db
- it call statefuklset, for mysql,
```
Deployment=for stateLess Apps
StatefulSet= for stateFUL apss or Databases
```
stateful set is harder to do than deploment


db are often hosted outside of kubernetes cluster
# k8s configurations
 - everything must go through api server
 - in Yaml or json format
```
apiVersion: apps/v1  # Using the apps/v1 API group/version
kind: Deployment     # This is a Deployment kind
metadata:
  name: my-deployment        # Name of the deployment
  labels:
    app: my-app              # Label for easy filtering
spec:
  replicas: 3                # We want 3 replicas of our pod
  selector:
    matchLabels:
      app: my-app            # Selector to match pods with label app=my-app
  template:                 # Pod template
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-container  # Name of the container within the pod
        image: my-image:latest  # Image to use for the container

```
# how it auto healing
 - so it will check the status data of the etcd with the taml file to do the thing
# kubectl
 -  comand line for control the worker node
# minikube cluster
 - one machine but mutiple node
 - cloud cluster - more machine and more node

# command

```
# -------------------
# Kubernetes (kubectl)
# -------------------

# Get Information
# kubectl get nodes
# kubectl get pods
# kubectl get svc
# kubectl get deployments
# kubectl get all -n [NAMESPACE]

# Create/Apply Resources
# kubectl create -f [FILE.yaml]
# kubectl apply -f [FILE.yaml]

# Delete Resources
# kubectl delete -f [FILE.yaml]
# kubectl delete pod [POD_NAME]

# Logs & Debugging
# kubectl logs [POD_NAME]
# kubectl describe [RESOURCE_TYPE] [RESOURCE_NAME]

# Accessing Cluster
# kubectl exec -it [POD_NAME] -- [COMMAND]
# kubectl port-forward svc/[SERVICE_NAME] [LOCAL_PORT]:[REMOTE_PORT]

# -------------------
# Minikube
# -------------------

# Cluster Management
# minikube start
# minikube stop
# minikube delete

# Interacting with Cluster
# minikube ip
# minikube dashboard
# minikube ssh

# Services & Networking
# minikube service list
# minikube service [SERVICE_NAME]

# Configuration and Environment
# minikube config view
# minikube config set [PROPERTY] [VALUE]
# minikube docker-env

# Addons
# minikube addons list
# minikube addons enable [ADDON_NAME]
# minikube addons disable [ADDON_NAME]

```
