# Kubernetes Command Handbook

A curated collection of commonly used **kubectl** commands organized by topic.

## Table of Contents

- [kubectl Basics](./kubectl_basics/README.md)
- [Pods and Controllers](./pods_and_controllers/README.md)
- [Deployments and ReplicaSets](./deployments_and_replicasets/README.md)
- [Services and Networking](./services_and_networking/README.md)
- [Ingress and Load Balancing](./ingress_and_load_balancing/README.md)
- [ConfigMaps and Secrets](./configmaps_and_secrets/README.md)
- [Volumes and Persistent Storage](./volumes_and_persistent_storage/README.md)
- [RBAC and Service Accounts](./rbac_and_service_accounts/README.md)
- [Helm Charts](./helm_charts/README.md)
- [Advanced Commands (debugging, logs, etc.)](./advanced_commands/README.md)
- [Cluster Management (kubeadm, kubelet, etc.)](./cluster_management/README.md)

Feel free to contribute! Fork the repository and submit a pull request with additional commands or improvements.

> A comprehensive, topic-wise collection of Kubernetes (`kubectl`) commands with explanations, syntax, practical examples, troubleshooting tips, interview notes, and production-ready use cases.

![Kubernetes](https://img.shields.io/badge/Kubernetes-v1.30+-326CE5?logo=kubernetes&logoColor=white)
![Documentation](https://img.shields.io/badge/Documentation-Complete-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Contributions](https://img.shields.io/badge/Contributions-Welcome-brightgreen)

---

## 📖 About

This repository is designed to serve as a one-stop reference for Kubernetes commands. Whether you're a beginner learning Kubernetes, preparing for CKA/CKAD exams, or a DevOps engineer working in production, you'll find commands organized by topic with clear explanations and real-world examples.

---

## 🎯 Objectives

- Learn Kubernetes commands topic by topic.
- Understand when and why to use each command.
- Prepare for CKA & CKAD certification exams.
- Improve Kubernetes troubleshooting skills.
- Build a quick reference for daily DevOps tasks.

---

# 📚 Table of Contents

- [01. Kubectl Basics](docs/01-Basics/)
- [02. Cluster Information](docs/02-Cluster-Information/)
- [03. Contexts & Configuration](docs/03-Contexts/)
- [04. Namespaces](docs/04-Namespaces/)
- [05. Pods](docs/05-Pods/)
- [06. Labels & Selectors](docs/06-Labels-and-Selectors/)
- [07. ReplicaSets](docs/07-ReplicaSets/)
- [08. Deployments](docs/08-Deployments/)
- [09. Services](docs/09-Services/)
- [10. ConfigMaps](docs/10-ConfigMaps/)
- [11. Secrets](docs/11-Secrets/)
- [12. Volumes](docs/12-Volumes/)
- [13. Persistent Volumes](docs/13-Persistent-Volumes/)
- [14. Persistent Volume Claims](docs/14-Persistent-Volume-Claims/)
- [15. Storage Classes](docs/15-StorageClasses/)
- [16. StatefulSets](docs/16-StatefulSets/)
- [17. DaemonSets](docs/17-DaemonSets/)
- [18. Jobs](docs/18-Jobs/)
- [19. CronJobs](docs/19-CronJobs/)
- [20. Init Containers](docs/20-InitContainers/)
- [21. Sidecar Containers](docs/21-SidecarContainers/)
- [22. Probes](docs/22-Probes/)
- [23. Scheduling](docs/23-Scheduling/)
- [24. Node Affinity](docs/24-Node-Affinity/)
- [25. Taints & Tolerations](docs/25-Taints-and-Tolerations/)
- [26. Network Policies](docs/26-NetworkPolicies/)
- [27. Ingress](docs/27-Ingress/)
- [28. RBAC](docs/28-RBAC/)
- [29. Service Accounts](docs/29-ServiceAccounts/)
- [30. Security Context](docs/30-SecurityContext/)
- [31. Helm](docs/31-Helm/)
- [32. Horizontal Pod Autoscaler](docs/32-HPA/)
- [33. Vertical Pod Autoscaler](docs/33-VPA/)
- [34. Cluster Autoscaler](docs/34-Cluster-Autoscaler/)
- [35. Debugging & Troubleshooting](docs/35-Debugging/)
- [36. Logs & Events](docs/36-Logs-and-Events/)
- [37. JSONPath](docs/37-JSONPath/)
- [38. Production Commands](docs/38-Production/)
- [39. Interview Commands](docs/39-Interview/)
- [40. CKA Cheat Sheet](docs/40-CKA/)

---

# 📂 Repository Structure

```
kubernetes-command-handbook
│
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
│
├── docs/
│   ├── 01-Basics/
│   ├── 02-Cluster-Information/
│   ├── 03-Contexts/
│   ├── ...
│   └── 40-CKA/
│
├── examples/
├── images/
├── assets/
└── scripts/
```

---

# 📝 Command Format

Each command is documented using the following structure:

```markdown
## Command Name

### Purpose
Brief explanation of what the command does.

### Syntax
kubectl ...

### Example
kubectl ...

### Output
Sample output (if applicable)

### Use Case
Real-world scenario.

### Common Mistakes
Things to avoid.

### Related Commands
Useful related commands.
```

---

# 🚀 Features

- ✅ Topic-wise organization
- ✅ Beginner-friendly explanations
- ✅ Practical examples
- ✅ Production use cases
- ✅ Troubleshooting commands
- ✅ CKA & CKAD preparation
- ✅ Interview-focused commands
- ✅ YAML generation shortcuts
- ✅ Kubectl tips & tricks
- ✅ Regularly updated

---

# 🎓 Who Is This Repository For?

- Students
- Beginners learning Kubernetes
- DevOps Engineers
- Platform Engineers
- Site Reliability Engineers (SRE)
- Cloud Engineers
- Kubernetes Administrators
- CKA & CKAD Aspirants

---

# 🤝 Contributing

Contributions are welcome!

You can contribute by:

- Adding new commands
- Improving explanations
- Fixing mistakes
- Adding production examples
- Improving documentation

Please open an Issue or submit a Pull Request.

---

# ⭐ Support

If you find this repository useful:

- ⭐ Star this repository
- 🍴 Fork it
- 📢 Share it with others

---

# 📄 License

This project is licensed under the MIT License.

---

# 📬 Connect

If this repository helped you, feel free to connect and contribute to making it one of the best Kubernetes command references available.

Happy Learning! 🚀