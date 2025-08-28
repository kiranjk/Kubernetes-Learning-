# 🚀 Kubernetes Pod Setup (Using Minikube)

This guide will help you quickly set up a Kubernetes cluster locally using **Minikube** and deploy your first **Pod**.

---

## 1️⃣ Install kubectl

`kubectl` is the command-line tool for interacting with Kubernetes clusters.  
Follow the official docs for installation:  
👉 [Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

---

## 2️⃣ Install Minikube

Minikube allows you to run Kubernetes locally.  
👉 [Install Minikube](https://minikube.sigs.k8s.io/docs/start/)

Start the cluster:
```bash
minikube start
3️⃣ Create pod.yaml
Define your pod configuration in a YAML file. Example:

yaml
Copy code
apiVersion: v1
kind: Pod
metadata:
  name: my-first-pod
spec:
  containers:
    - name: nginx-container
      image: nginx
      ports:
        - containerPort: 80

4️⃣ Apply the Pod Configuration
Use kubectl to create the pod:

bash
Copy code
kubectl apply -f pod.yaml
5️⃣ Verify the Pod
Check if your pod is running:

bash
Copy code
kubectl get pods

<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/cd96d7b8-52b2-46d4-a098-d45c6faf160b" />


