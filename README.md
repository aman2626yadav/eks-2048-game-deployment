# eks-2048-game-deployment
Deploying the 2048 game on Amazon EKS using Kubernetes with AWS ALB Ingress Controller.
2048 Game Deployment on Amazon EKS with ALB Ingress
# Project Overview
This project demonstrates deploying a containerized 2048 web application on a Kubernetes cluster using Amazon EKS.
The application is exposed to the internet using AWS Application Load Balancer (ALB) Ingress managed by the AWS Load Balancer Controller.
The project showcases practical DevOps and Cloud engineering skills, including Kubernetes cluster provisioning, ingress configuration, and cloud load balancing.
# Tech Stack
AWS EKS (Elastic Kubernetes Service)
Kubernetes
AWS Load Balancer Controller
Application Load Balancer (ALB)
kubectl
eksctl
AWS CLI
Docker
Linux (Ubuntu EC2)

# Architecture

Internet
↓
AWS Application Load Balancer (ALB)
↓
Kubernetes Ingress
↓
Kubernetes Service
↓
Kubernetes Pods (2048 Game)

⚙️ Implementation Steps

1️⃣ Create EKS Cluster
eksctl create cluster --name demo-cluster --region us-east-1 --fargate

2️⃣ Configure kubectl
aws eks update-kubeconfig --region us-east-1 --name demo-cluster

3️⃣ Install AWS Load Balancer Controller

Deploy the controller required to create and manage AWS ALB resources through Kubernetes.

4️⃣ Deploy the 2048 Application
kubectl apply -f https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/main/docs/examples/2048/2048_full.yaml
5️⃣ Verify Deployment
kubectl get pods -n game-2048
kubectl get svc -n game-2048
kubectl get ingress -n game-2048
🌐 Application Access

Retrieve the load balancer endpoint:

kubectl get ingress -n game-2048

Example output:

http://k8s-game2048-ingress2-bcac0b5b37-196753871.us-east-1.elb.amazonaws.com

Open the URL in a browser to access the 2048 game application.

#Key Learnings
Deploying applications on Kubernetes using Amazon EKS
Configuring ALB Ingress with AWS Load Balancer Controller
Managing Kubernetes resources (Pods, Services, Ingress)
Exposing Kubernetes workloads to the internet using AWS ALB

for proof above the folder hava  a screenshort
