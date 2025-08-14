# Kubernetes-Learning-🐳☸️

A simple guide to understanding Kubernetes fundamentals.

Kubernetes Main Components
Kubernetes has two main components:

1️⃣ Control Plane (Master Node) – Manages and controls the cluster.
2️⃣ Data Plane (Worker Node) – Executes workloads (where the actual applications run).

# Control Plane Components 🧠

API Server – Accepts requests from the external world (kubectl, APIs, etc.).

**Scheduler** – Assigns workloads (Pods) to specific nodes.

**etcd** – Stores the cluster’s configuration and state.

**Controller Manager** – Ensures the desired state of the cluster is maintained.

# Data Plane Components 💪

**Kubelet** – Ensures that Pods are running; informs the Control Plane if a Pod fails so it can be recreated.

**Kube Proxy** – Manages networking and assigns IP addresses for services.

**Container Runtime** – Runs the containers (e.g., Docker, containerd).

💡 Tip: Master Node = brains 🧠 | Worker Node = muscles 💪


<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/01efd951-39b5-4e10-b98f-314277dbd641" />





