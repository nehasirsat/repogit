Todo-App Deployment on Kubernetes


This guide provides instructions for deploying a sample todo-app on Kubernetes, scaling the application, and configuring Persistent Volumes and Persistent Volume Claims.
Prerequisites
* Kubernetes cluster (e.g., Minikube, Docker Desktop Kubernetes, or a cloud-based Kubernetes cluster)
* kubectl command-line tool

Steps to Deploy Todo-App
* add a deployment.yml file (sample is kept in the folder for your reference)
* apply the deployment to your k8s (minikube) cluster by command kubectl apply -f deployment.yml

Scaling the application
To scale the todo-app deployment:
kubectl scale deployment/todo-app-deployment --replicas=3
Replace 3 with the desired number of replicas.


Creating PV and PVC
1.Create Persistent Volume	
Create a Persistent Volume (PV) YAML file (pv.yaml) and    apply it using following command:
   kubectl apply -f pv.yaml
2. Create Persistent Volume Claim
Create a Persistent Volume Claim (PVC) YAML file (pvc.yaml) and apply it using following command:
   kubectl apply -f pvc.yaml
3.Apply the deployment
 Update the todo-app deployment to use the PVC and apply the updated deployment
kubectl apply -f deployment.yaml
Connect to a Pod in your Deployment using command :
 `kubectl exec -it -- /bin/bash

Verify that the Persistent Volume has been added to your Deployment by checking the status of the Pods and Persistent Volumes in your cluster. Use this commands kubectl get pods ,
kubectl get pv. 
