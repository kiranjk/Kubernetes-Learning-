# 🌐 Kubernetes Services

In Kubernetes, Pods are **ephemeral** (temporary).  
- If a Pod crashes, the **ReplicaSet** creates a new one.  
- But the new Pod gets a **different IP address** each time.  
👉 This makes it difficult for users or other applications to connect directly to Pods.

That’s why we need **Services**.  

---

## 🎯 Why Services?
A **Service** provides a **stable IP/DNS name** and ensures traffic always reaches the correct Pods.  
It works using **labels and selectors**:
- You add **labels** in your Deployment (e.g., `app: nginx`).
- The Service uses a **selector** to track Pods with that label.
- Even if Pods crash and restart, the Service always routes traffic to the new Pods automatically.  

✅ This makes applications reliable, highly available, and user-friendly.  

---

## 🔹 What Services Offer
- **Service Discovery** → Stable DNS name for Pods.  
- **Load Balancing** → Distributes traffic across multiple Pods.  
- **Exposure** → Decide how your application is accessed (inside cluster, node, or outside world).  

---

## 🔹 Types of Services

### 1️⃣ ClusterIP (Default)
- Accessible **only within the cluster**.  
- Used for **internal communication** between services.  
```bash
kubectl expose deployment my-deployment --type=ClusterIP --port=80 --name=clusterip-service

2️⃣ NodePort
Makes the Service accessible on a Node’s IP and a static port (30000–32767).

Used for testing or internal VPC access.

bash
Copy code
kubectl expose deployment my-deployment --type=NodePort --port=80 --name=nodeport-service

3️⃣ LoadBalancer
Exposes the Service to the outside world (via cloud provider’s LoadBalancer).

Used for production when apps need to be publicly available.

bash
Copy code
kubectl expose deployment my-deployment --type=LoadBalancer --port=80 --name=load

📊 Quick Workflow

User sends request → reaches Service (fixed IP/DNS).

Service uses labels → finds matching Pods.

Service load balances traffic → sends request to one healthy Pod.

If a Pod crashes → ReplicaSet creates new Pod → Service automatically tracks it.

✅ Result: Stable, resilient, and highly available applications.

📝 Summary

Pods = Ephemeral (change IPs often)

ReplicaSet = Ensures desired Pod count

Service = Stable endpoint + Load Balancer + Service Discovery

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/efd2e26b-5876-4647-9c9b-46321d58f589" />
