

# 🚀 Node.js Kubernetes Deployment

This project demonstrates how to **containerize a Node.js app** and **deploy it on Kubernetes** using Minikube and Docker Hub.

## 📌 Prerequisites
Make sure you have the following installed on your system:
- [Docker](https://www.docker.com/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [Kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Node.js](https://nodejs.org/en/)

---

## 🛠 Steps to Run the Project

### 1 Clone the Repository
```sh
git clone git@github.com:deveshanurag/node-k8s-app.git
cd node-k8s-app
```

### 2 Build & Push the Docker Image to Docker Hub
- Login to **Docker Hub**:
  ```sh
  docker login
  ```
- Build the Docker image:
  ```sh
  docker build -t your-dockerhub-username/node-k8s-app .
  ```
- Tag the image:
  ```sh
  docker tag your-dockerhub-username/node-k8s-app your-dockerhub-username/node-k8s-app:latest
  ```
- Push the image to Docker Hub:
  ```sh
  docker push your-dockerhub-username/node-k8s-app:latest
  ```

---

## 🏗️ Deploying to Kubernetes

### 3 Start Minikube
```sh
minikube start
```

### 4 Create Kubernetes Deployment Configuration
Create a **deployment.yml** file for the Kubernetes Deployment.
Change the **deployment.yml** file at line 17 to your-dockerhub-username/node-k8s-app:latest

### 5 Create Kubernetes Service Configuration
Create a **service.yml** file for the Kubernetes Service.

### 6 Apply Kubernetes Configuration
- Deploy the application:
  ```sh
  kubectl apply -f deployment.yml
  kubectl apply -f service.yml
  ```

- Check the status:
  ```sh
  kubectl get pods
  kubectl get services
  ```

### 7 Access the Application
- Get the **NodePort**:
  ```sh
  minikube service node-app-service --url
  ```
- Open the URL in a browser to see your app running.

---

## 🛑 Stopping & Cleaning Up
- To stop everything:
  ```sh
  kubectl delete -f deployment.yml
  kubectl delete -f service.yml
  minikube stop
  ```

---

## 🎯 Summary
✔️ Created a simple **Node.js app**  
✔️ Containerized it using **Docker**  
✔️ Pushed the image to **Docker Hub**  
✔️ Deployed it using **Kubernetes** on Minikube  
✔️ Exposed it using a **Kubernetes Service**  

---
