# Interview Questions & Critical Commands

In Kubernetes and DevOps interviews (and certifications like CKA/CKAD), certain commands are tested repeatedly. This guide compiles the most important commands and diagnostic questions you should master for interviews.

### 1. Generating Manifests Instantly (Time Management)
In hands-on interviews/exams, you should never write YAML from scratch. Use imperative commands with `--dry-run=client -o yaml`.
* **Pod Template:**
  ```bash
  kubectl run nginx --image=nginx --dry-run=client -o yaml > pod.yaml
  ```
* **Deployment with Replicas & Port:**
  ```bash
  kubectl create deployment web-app --image=nginx --replicas=3 --port=80 --dry-run=client -o yaml > deploy.yaml
  ```
* **Service exposing a port:**
  ```bash
  kubectl create service clusterip web-svc --tcp=80:8080 --dry-run=client -o yaml > svc.yaml
  ```

### 2. Node Operations & Maintenance (CKA Favorite)
How do you safely reboot a node or take it offline?
* **Cordon the node** (prevent new pods):
  ```bash
  kubectl cordon <node-name>
  ```
* **Drain the node** (evict existing pods safely):
  ```bash
  kubectl drain <node-name> --ignore-daemonsets --delete-emptydir-data --force
  ```
* **Bring the node back online**:
  ```bash
  kubectl uncordon <node-name>
  ```

### 3. Troubleshooting CrashLoopBackOff & Failed Pods
What commands do you use when a Pod is stuck in `CrashLoopBackOff` or `Pending`?
* **Check the events list** (especially for `Pending` pods due to scheduling issues/taints/limits):
  ```bash
  kubectl describe pod <pod-name>
  ```
* **View logs of a container that crashed** (crucial for `CrashLoopBackOff`):
  ```bash
  kubectl logs <pod-name> --previous
  ```
* **View events across the namespace sorted by time**:
  ```bash
  kubectl get events --sort-by='.metadata.creationTimestamp'
  ```

### 4. Advanced JSONPath Filtering
Interviews often test your ability to extract specific fields programmatically.
* **Get Node Internal IPs:**
  ```bash
  kubectl get nodes -o jsonpath='{.items[*].status.addresses[?(@.type=="InternalIP")].address}'
  ```
* **Sort Pods by restarts:**
  ```bash
  kubectl get pods --sort-by='.status.containerStatuses[0].restartCount'
  ```

### 5. Context & Namespace Configurations
How do you switch namespaces or clusters efficiently?
* **Set namespace for current context permanently:**
  ```bash
  kubectl config set-context --current --namespace=<namespace-name>
  ```
* **View current context name:**
  ```bash
  kubectl config current-context
  ```

### 6. Security & RBAC Checks
How do you verify authorization and permissions?
* **Check if you (or a service account) can perform an action:**
  ```bash
  kubectl auth can-i create deployments
  kubectl auth can-i get secrets --as=system:serviceaccount:default:my-sa
  ```

Feel free to extend this list with additional questions, scenarios, and commands that are frequently tested in interviews.
