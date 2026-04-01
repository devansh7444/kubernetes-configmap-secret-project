# Kubernetes ConfigMap and Secret Project

## 📌 Project Overview

This project demonstrates how to use **Namespace, ConfigMap, Secret, and Pod** in Kubernetes.
The application runs an **Nginx container** that reads configuration values from a **ConfigMap** and sensitive credentials from a **Secret**.

This project helps understand how configuration and secrets are managed securely in **Kubernetes environments**.

---

## 🧰 Technologies Used

* Kubernetes
* kubectl
* YAML
* Nginx container
* Git & GitHub

---

## 📂 Project Structure

```
kubernetes-configmap-secret-project
│
├── namespace.yaml
├── configmap.yaml
├── secret.yaml
├── pod.yaml
└── README.md
```

---

## ⚙️ Kubernetes Resources Used

### 1️⃣ Namespace

Creates a logical environment called **dev** to isolate resources.

```
namespace.yaml
```

---

### 2️⃣ ConfigMap

Stores application configuration values such as:

* APP_ENV
* APP_VERSION

```
configmap.yaml
```

---

### 3️⃣ Secret

Stores sensitive data like database credentials.

```
secret.yaml
```

Credentials used in this project:

* username
* password

---

### 4️⃣ Pod

Runs an **Nginx container** that reads:

* Environment variables from ConfigMap
* Credentials from Secret

```
pod.yaml
```

---

## 🚀 How to Run the Project

### Step 1: Start Kubernetes Cluster

If using Minikube:

```
minikube start
```

---

### Step 2: Deploy Resources

Run the following command inside the project folder:

```
kubectl apply -f .
```

---

### Step 3: Verify Deployment

Check namespace:

```
kubectl get namespaces
```

Check resources:

```
kubectl get all -n dev
```

---

### Step 4: Verify Environment Variables

Access the pod:

```
kubectl exec -it app-pod -n dev -- /bin/bash
```

Check environment variables:

```
env
```

Expected output:

```
APP_ENV=development
DB_USERNAME=admin
DB_PASSWORD=password123
```

---

## 📊 Architecture

```
Kubernetes Cluster
        │
        ▼
   Namespace (dev)
        │
 ┌───────────────┬───────────────┐
 │               │               │
ConfigMap      Secret           Pod
(App Config)  (DB Credentials)  (Nginx Container)
```

---

## 🎯 Learning Outcomes

* Understand Kubernetes Namespaces
* Learn how to use ConfigMaps for configuration
* Store sensitive data using Secrets
* Access configuration and secrets inside containers
* Deploy Kubernetes resources using YAML

---

## 👨‍💻 Author

Devansh Motghare

GitHub: https://github.com/devansh7444
