
####Assignment - Scalable Services - Deployment - Minikube , Kubernets####
 (Module - Deployment via Minikube, Kubernets: Author - Pamuru KesavaKumar, BITS ID - 2020mt93550)

List of Services 	
1. Book Service - Python, Flask, Sqlite3
2. Inventory Service  - Django, Python, SQLite3
3. Student Service - Node Js, Javascript, Npm, Mongo DB
4. Library Service - Maven Java, MySQL, Rabbit MQ	
5. Notification - - Maven Java, Rabbit MQ

***Code Base**
npm https://github.com/GaneshKoushik313/student_records
Django https://github.com/singhTarunPal/inventoryService
Flask https://github.com/singhTarunPal/bookService	  
Mevan Java https://github.com/singhTarunPal/libraryService
	Dependency - MySQL, Rabbit MQ	
Mevan Java https://github.com/singhTarunPal/notificationService
   Dependency - Rabbit MQ

****Deployment - Minikube, Kubernets ****
Deployment - https://github.com/kumarp3451/Minikube_Kubernets_Deployment


********Deployment Steps - Minikube, KuberNets ***********

	a. Minikube			
			Minikube is a utility you can use to run Kubernetes (k8s) on your local machine. 
			It creates a single node cluster contained in a virtual machine (VM). 
			This cluster lets you demo Kubernetes operations without requiring the time and resource-consuming installation of full-blown K8s.

	b. Kubernets
		Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.
	
		"Deployment"—configured and operational resources. Deployments are the overall processes that enable you to orchestrate your resources.
		"ReplicaSet"—sets of pods that provide the resources for your services.
		"Pod"—a unit that contains one or more containers along with attached storage resources, and configuration definitions. Pods are grouped together in 
		 ReplicaSets and all pods in a set run the same container images.
		"Node cluster"—control plane and worker nodes that each contain one or more pods. The workers run your workloads and the control plane orchestrates 
		 the workers together. This is what is created by Minikube.
		"Node processes"—the various components that you use to connect and manage Kubernetes. Control plane processes include API servers, ectd, Scheduler, 
		 kube-controller-manager, and cloud-controller-manager. Worker processes include kubelet, kube-proxy, and your container runtime.
		"Container"—the image you create to hold your applications.

	

#### 1.Book Service Deployment - Flask (Python) ####

# git clone  https://github.com/singhTarunPal/bookService	

#Create YAML file with extenstion as .yaml 
	deployment.yaml - its configuration file used to deploy api/services in kubernets.

#Build the service 
	docker build -t flask-book-service .

#Check Docker Image is created or not	
	docker image ls
	
#Minikube start
	minikube start

#Load the latest docker image created
	minikube image load flask-book-service:latest
	
# Deploy
	kubectl apply -f deployment.yaml


#Minikube Dashboard
	minikube dashboard


#### 2.Inventory Service Deployment - Django (Python) ####

# git clone  https://github.com/singhTarunPal/inventoryService	

#Create YAML file with extenstion as .yaml 
	deployment.yaml - its configuration file used to deploy api/services in kubernets.

#Build the service 
	docker build -t django-inventory-service .

#Check Docker Image is created or not	
	docker image ls
	
#Minikube start
	minikube start

#Load the latest docker image created
	minikube image load django-inventory-service:latest
	
# Deploy
	kubectl apply -f deployment.yaml


#Minikube Dashboard
	minikube dashboard
	
	minikube image load npm-java-student-service:latest
	
	
	
#### 3.Student Service Deployment - Node Js, Javascript, Npm (Python) 

#git clone https://github.com/GaneshKoushik313/student_records

#Create YAML file with extenstion as .yaml 
	deployment.yaml - its configuration file used to deploy api/services in kubernets.

#Build the service 
	docker build -t npm-java-student-service .

#Check Docker Image is created or not	
	docker image ls
	
#Minikube start
	minikube start

#Load the latest docker image created
	minikube image load npm-java-student-service:latest
	
# Deploy
	kubectl apply -f deployment.yaml


#Minikube Dashboard
	minikube dashboard
	
		

	
****Additional Commands ***

Docker Images
docker run -d --name npm-java-student-service -p 8080:5000 npm-java-student-service

kubectl get pods
kubectl get services
kubectl delete deployment <servicename>

Minikube delete
	
	
	
	
	
	
