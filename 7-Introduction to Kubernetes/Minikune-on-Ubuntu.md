# Setup Single Node Kubernetes Cluster with Minikube on Ubuntu
## What is Minikube?
- Minikube is a tool which will help us to easily run kubernetes locally.

- Minikube runs as a single node kubernetes cluster inside a VM on the laptop for the users who want to try kubernetes and test codes locally on the kubernetes environment.

- Minikube is available for Linux , Windows and MacOS.

## Features supported by Minikube
- Container Runtime such as containerd , Docker , CRI-O
- Dashboards
- ConfigMaps and Secrets
- DNS
- NodePorts
- Ingress

## Checklist
- Before installing minikube on the Local systems , We need to check If virtualization is supported on the local system.

- Check in Ubuntu
```
sudo grep -E --color 'vmx|svm' /proc/cpuinfo
```

- To check the virtualization compatibility on MacOS , Run this command.
```
sysctl -a | grep -E --color 'machdep.cpu.features|VMX'
```

- To check if the virtualization is supported on Windows , Run this command.
```
systeminfo
```

## Prerequisites
- kubectl should be installed
- VirtualBox should be installed

```
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
kubectl version --client
```

## Single node kubernetes cluster

```
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube
sudo mv minikube /usr/local/bin/minikube
minikube version
```

- To check the lists of available minikube commands , Run,
```
minikube
```

- Launch a VM in the virtual box where the cluster will be launched and so it will take some time for the minikube to launch the cluster.
```
minikube start
```

- Now we have the running kubernetes cluster locally.

- To check the status of the cluster , Run the following command.
```
minikube status
```

- To manage the objects or to control the resources of kubernetes objects such as pods . deployment , services , volumes etc , We can launch the minikube kubernetes dashboard so that we can manage everything graphically.
```
minikube dashboard
```

- To get the Cluster information,
```
kubectl cluster-info
```

- To get the lists of nodes in the cluster , Run the below command,
```
kubectl get nodes
```


- To list the pods running within the cluster,
```
kubectl get pods
```

- To list the pods across all namespaces,
```
kubectl get pods --all-namespaces
```


## Deploying Apps into Kubernetes Cluster using Kubectl
- Lets deploy our first app on kubernetes cluster with the kubectl commands.
- We will deploy the existing image named echoserver , which is a simple HTTP server.
```
kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.10
```

```
kubectl get deployments
```


```
kubectl get po -o wide
```

```
kubectl expose deployment hello-minikube --type=NodePort --port=8080
```

```
kubectl get svc
```

```
minikube service hello-minikube --url
```


- If you copy and paste the URL in the browser , You should get the response

- Now Head over to the Kubernetes Dashboard and then click Deployments ,

- Here you can find the deployments that we have made using kubectl.

- Click Pods , To list the pods running in the kubernetes cluster,

## Terminating Local Kubernetes Cluster
- After the testing is completed , We can terminate the single node kubernetes cluster which we are running locally using minikube.

- Before terminating the cluster , We need to remove the pods and services and deployments which are actively running in the cluster.

- To terminate the Services , Run the below command.

```
kubectl delete service hello-minikube
```

- Using the below command , We can delete the pods
```
kubectl delete pods hello-minikube-64b64df8c9-7lgxg
```

- To delete the deployments,
```
kubectl delete deployment hello-minikube
```

- After all the resources are deleted from the kubernetes cluster , We can terminate the kubernetes cluster.
```
minikube delete
```

- Finally , Run the below command to verify the cluster status.
```
minikube status
```
