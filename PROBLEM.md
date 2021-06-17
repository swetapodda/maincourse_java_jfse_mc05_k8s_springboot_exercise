## Exercise: Deploy a Spring Boot microservice application on a K8s Cluster

* In this Exercise, you will deploy a Spring Boot microservice application on K8s Cluster.

To complete the exercise, first perform the following installations:
1.  Install a Hypervisor: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
2.  Install and Set up kubectl: [https://kubernetes.io/docs/tasks/tools/install-kubectl/](https://kubernetes.io/docs/tasks/tools/install-kubectl/)    
3.  Install Minikube: [https://kubernetes.io/docs/tasks/tools/install-minikube/](https://kubernetes.io/docs/tasks/tools/install-minikube/)
     

This exercise contains the following empty files in the k8-manifests folder

		- springboot-deployment.yml- to create the deployment
		- springboot-svc.yml- to create service of type NodePort to expose the deployed Spring Boot application


For defining Deployment and Service, understand and do the following steps:

	1. Build, tag, and push the Spring Boot application image to Docker Hub.
	2. Define a deployment in `springboot-deployment.yml` by using the image pushed to Docker Hub in the previous step.
	3. Define a service in `springboot-svc.yml` of type `NodePort` and use the 
	4. created deployment in the above step as a selector.



For Deploying and verifying, follow the below steps:

	1. Open terminal and cd into the folder where yml files created above are present.
	2. Start the Minikube cluster. And `minikube status` to make sure that the Minikube cluster is running.
	3. Run command `kubectl apply -f springboot-deployment.yml` and `kubectl apply -f springboot-svc.yml` to submit resource definitions to Kubernetes.
	4. Run command `kubectl get pods` to watch your Pods coming alive.
	5. Run command `minikube ssh` to SSH to minikube vm.
	6. Run command `curl <container1 IP>:port/<mapping>` to verify that the service is working.
	7. Run command `curl <container2 IP>:port/<mapping>` to verify that the service is working.
	8. Run command `kubectl describe svc <svc-name>` to fetch details about the Service.
	9. Run command `minikube ip` to get the IP of the cluster node.
	10. Open `http://<minikube-ip>:<nodePort>/message` URL on the browser to verify the working of the container.

### Instructions
- Take care of whitespace/trailing whitespace
- Do not change the provided code unless instructed
- Ensure your code compiles without any errors/warning/deprecations
- Follow best practices while coding