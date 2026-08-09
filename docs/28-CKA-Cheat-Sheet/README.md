# Certified Kubernetes Administrator (CKA) Cheat Sheet

This is an extensive reference cheat sheet designed for speed and accuracy during the Certified Kubernetes Administrator (CKA) exam.

---

## 1. Exam Environment & Setup (Do This First!)
Always configure your shell environment for fast typing, aliases, and variables.
```bash
# Setup kubectl autocomplete and alias
alias k=kubectl
complete -o default -F __start_kubectl k

# Fast dry-run variables
export do="--dry-run=client -o yaml"
export now="--force --grace-period=0"

# Usage examples:
# k run nginx --image=nginx $do
# k delete pod nginx $now
```

---

## 2. Cluster Architecture & Maintenance

### ETCD Backup & Restore
* **Backup ETCD Snapshot:**
  ```bash
  ETCDCTL_API=3 etcdctl --endpoints=https://127.0.0.1:2379 \
    --cacert=/etc/kubernetes/pki/etcd/ca.crt \
    --cert=/etc/kubernetes/pki/etcd/server.crt \
    --key=/etc/kubernetes/pki/etcd/server.key \
    snapshot save /opt/etcd-backup.db
  ```
* **Restore ETCD Snapshot:**
  ```bash
  ETCDCTL_API=3 etcdctl --data-dir=/var/lib/etcd-from-backup \
    snapshot restore /opt/etcd-backup.db
  ```
  *(Note: After restoring, you must update the hostPath volume path in `/etc/kubernetes/manifests/etcd.yaml` to point to `/var/lib/etcd-from-backup`).*

### Kubeadm Upgrade (Control Plane Node)
1. **Upgrade kubeadm:**
   ```bash
   apt-mark unhold kubeadm && apt-get update && apt-get install -y kubeadm=1.30.0-1.1 && apt-mark hold kubeadm
   ```
2. **Plan & Apply Upgrade:**
   ```bash
   kubeadm upgrade plan
   kubeadm upgrade apply v1.30.0
   ```
3. **Upgrade kubelet and kubectl:**
   ```bash
   apt-mark unhold kubelet kubectl && apt-get install -y kubelet=1.30.0-1.1 kubectl=1.30.0-1.1 && apt-mark hold kubelet kubectl
   ```
4. **Restart Services:**
   ```bash
   systemctl daemon-reload
   systemctl restart kubelet
   ```

---

## 3. Workloads & Scheduling

### Static Pods
* Static pods are managed directly by the kubelet on a specific node.
* Find the directory path in `/var/lib/kubelet/config.yaml` under `staticPodPath` (usually `/etc/kubernetes/manifests`).
* **Identify running static pods:** They have the node name appended as a suffix (e.g. `kube-apiserver-controlplane`).

### Taints and Tolerations
* **Taint a node:**
   ```bash
   kubectl taint nodes node-1 key1=value1:NoSchedule
   ```
* **Remove a taint:**
   ```bash
   kubectl taint nodes node-1 key1=value1:NoSchedule-
   ```
* **Tolerations definition snippet (in Pod spec):**
  ```yaml
  tolerations:
  - key: "key1"
    operator: "Equal"
    value: "value1"
    effect: "NoSchedule"
  ```

---

## 4. Services, Networking & Ingress

### CoreDNS & DNS Resolution
* If Pods cannot resolve service names, inspect DNS service and endpoints:
  ```bash
  kubectl get svc -n kube-system -l k8s-app=kube-dns
  kubectl get ep -n kube-system -l k8s-app=kube-dns
  ```
* Test DNS from a temporary pod:
  ```bash
  kubectl run busybox --image=busybox:1.28 --restart=Never --rm -it -- nslookup kubernetes.default
  ```

---

## 5. Storage (PV, PVC, and StorageClass)

### PV & PVC Mount Check
* Ensure your PVC storage capacity matches or is less than the PV capacity.
* Ensure matching `accessModes` (e.g. `ReadWriteOnce`).
* **Volume Mount Pod Spec Example:**
  ```yaml
  spec:
    volumes:
    - name: data-volume
      persistentVolumeClaim:
        claimName: my-pvc
    containers:
    - name: app
      image: nginx
      volumeMounts:
      - name: data-volume
        mountPath: /var/www/html
  ```

---

## 6. Troubleshooting Cluster Components

### Service Logs (Systemd)
If `kubectl` commands fail completely, SSH into the node and inspect system services:
```bash
# Check Kubelet status & logs
systemctl status kubelet
journalctl -u kubelet -f
journalctl -u kubelet --no-pager | tail -n 100

# Check Container Runtime status & logs
systemctl status containerd
journalctl -u containerd -f
```

### Static Pod Failures
If API server or Etcd static pod fails to start, look at container runtime logs directly:
```bash
# Using crictl (recommended tool for container diagnostics on nodes)
crictl ps -a
crictl logs <container-id>
```

Feel free to extend this list with additional custom CKA debugging commands and steps.
