# MONGO-WEB-APP WITH K8S CLUSTER. 
### Interact with web app and all k8s components will make app run on containerised enviroment. 

- This repository contains a simple web app created using Mongo and Mongo-express images from docker hub. 
- There is a K8s cluster being set-up with help of minikube. 
– K8's deployments, pods, secret, configmap are all used here. 
- This can be run on a local machine following steps mentioned in text files.
- This repository serves as a display of container orchestration. 

# To run the app follow these steps: 

# Prerequisities:
  - Docker Daemon (download docker desktop for your system)
  - Minikube (recommended to download via CLI using a package manager)
  - Kubectl  (recommended to download via CLI using a package manager)

# Make sure your cluster is up and running and run the app using these steps: 

#1. minikube start -> to start your cluster (initially it will take time also ensure before doing this your Docker Daemon is on) 
#2. minikube status -> check status of your conrtol plane, it should say "running" and "configured" 
#3. kubectl -> check if kubectl is downloaded, if so, this command lists all the basic command you can use. 


### Then run the configuration files (the k8s components) in order. 
### The deployment files here also have the service component inside of them, so both can be created/deployed at once. 
- Run the secret file
    - use command: kubectl apply -f mongo-secret.yaml 
- Run the mongodb pod (deployment file, it also consists of the service associated with it )
    - use command: kubectl apply -f mongo.yaml
- Run the configmap
    - use command: kubectl apply -f mongo-configmap.yaml
- Rund the mongo-express pod (deployment file, it also consists of the service associated with it)
    - use command: kubectl apply -f mongo-express.yaml

### Run "kubectl get all" to verify all resources are made. 
### Run the external service, that will open the browser and run the app, do so with the command: minkube service "service-name" 

End of instructions. 
