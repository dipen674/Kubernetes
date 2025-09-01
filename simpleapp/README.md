🍽️ Nginx Crispy Kitchen on Kubernetes
https://img.shields.io/badge/license-MIT-blue.svg

This project deploys the Crispy Kitchen static website using Nginx on Kubernetes with Minikube.

Requirements 🔧
text
- Minikube
- kubectl
- Docker
Installation 🔌
text
1. Ensure Minikube is running:
   minikube start

2. Deploy the application:
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
Accessing the Application 🌐
Check Pods Status
bash
kubectl get pods
Example output:

text
NAME                               READY   STATUS    RESTARTS   AGE
myapp-deployment-xxx               1/1     Running   0          1m
Check Services
bash
kubectl get services
Example output:

text
NAME            TYPE       CLUSTER-IP   EXTERNAL-IP   PORT(S)        AGE
myapp-service   NodePort   10.96.x.x    <none>        80:30080/TCP   1m
Access via Minikube
bash
minikube service myapp-service --url
Example output:

text
http://192.168.49.2:30080
Alternative: Port Forwarding
bash
kubectl port-forward service/myapp-service 8080:80
Access at: http://localhost:8080

Debugging 🔍
Check logs:

bash
kubectl logs -l app=myappnew
Describe pods:

bash
kubectl describe pod -l app=myappnew
Optional: Test Image Locally 🐳
bash
docker run -p 8080:80 <your-username>/nginx-crispy:latest
Access at: http://localhost:8080

Contributing 💡
If you want to contribute to this project and make it better with new ideas, your pull request is very welcomed.
If you find any issue just put it in the repository issue section, thank you.

Thank You!
Please ⭐️ this repo and share it with others.
