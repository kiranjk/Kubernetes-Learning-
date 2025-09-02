# 🚀 My First Kubernetes Deployment

## 🔹 What is a Deployment?
A **Deployment** in Kubernetes is a higher-level abstraction that manages your application pods.  
- It ensures the **desired number of replicas (pods)** are always running.  
- It supports **rolling updates**, **rollbacks**, and **scaling**.  
- It automatically replaces failed pods → making applications more **resilient**.  

---

## 🔹 What is a ReplicaSet?
A **ReplicaSet** ensures a specified number of pod replicas are running at all times.  
- If a pod crashes or is deleted, the ReplicaSet will automatically create a new one.  
- **Deployments internally use ReplicaSets** to manage pods.  

---

## 🔹 Example: Auto Healing
If you delete a pod manually:
```bash
kubectl delete pod <pod-name>
👉 Kubernetes will automatically create a new pod because the Deployment (through ReplicaSet) maintains the desired state.
This process is called Self-Healing, and it ensures no user impact.

📂 Example: my-first deployment.yaml

1️⃣ Create Deployment
bash
Copy code
kubectl apply -f my- first deployment.yaml
kubectl get deployments
kubectl get pods
2️⃣ Delete One Pod (Self-Healing Demo)
bash
Copy code
kubectl delete pod <pod-name>
kubectl get pods
👉 You’ll notice a new pod comes up automatically.

3️⃣ Scale Deployment
bash
Copy code
kubectl scale deployment my-deployment --replicas=5
kubectl get pods
4️⃣ Update Image
Edit YAML → change nginx:1.25 → nginx:1.26, then:

bash
Copy code
kubectl apply -f my-deployment.yaml
kubectl rollout status deployment/my-deployment
5️⃣ Rollback
bash
Copy code
kubectl rollout undo deployment/my-deployment
6️⃣ Delete Deployment
bash
Copy code
kubectl delete -f my-deployment.yaml
✅ With Deployments + ReplicaSets, Kubernetes ensures:

Scaling up/down apps easily.

Rolling updates & rollbacks.

Self-healing pods without user disruption.

🔹 Commands to Try
1️⃣ Create Deployment
kubectl apply -f my-deployment.yaml
kubectl get deployments
kubectl get pods

2️⃣ Delete One Pod (Self-Healing Demo)
kubectl delete pod <pod-name>
kubectl get pods


👉 You’ll notice a new pod comes up automatically.

3️⃣ Scale Deployment
kubectl scale deployment my-deployment --replicas=5
kubectl get pods

4️⃣ Update Image

Edit YAML → change nginx:1.25 → nginx:1.26, then:

kubectl apply -f my-deployment.yaml
kubectl rollout status deployment/my-deployment

5️⃣ Rollback
kubectl rollout undo deployment/my-deployment

6️⃣ Delete Deployment
kubectl delete -f my-deployment.yaml


✅ With Deployments + ReplicaSets, Kubernetes ensures:

Scaling up/down apps easily.

Rolling updates & rollbacks.

Self-healing pods without user disruption.

<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/5bc9a544-0218-4f7a-b093-a62997d9c4d2" />


yaml
Copy code
