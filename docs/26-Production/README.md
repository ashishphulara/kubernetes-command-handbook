# Production Commands

Managing Kubernetes in a production environment requires commands for zero-downtime deployments, safe node maintenance, resource utilization audits, certificate management, and cluster health checks. Here is a reference of essential production commands.

### Rollout & Deployment Management
| Command | Description | Example |
|---------|-------------|---------|
| `kubectl rollout status <resource>/<name>` | Watch the status of a rolling upgrade | `kubectl rollout status deployment/web-app` |
| `kubectl rollout history <resource>/<name>` | View history of revisions for a deployment | `kubectl rollout history deployment/web-app` |
| `kubectl rollout undo <resource>/<name>` | Roll back to the previous deployment revision | `kubectl rollout undo deployment/web-app` |
| `kubectl rollout restart <resource>/<name>` | Perform a rolling restart of all pods in a resource | `kubectl rollout restart deployment/web-app` |
| `kubectl scale <resource>/<name> --replicas=<num>` | Scale the number of replicas for a resource up or down | `kubectl scale deployment/web-app --replicas=10` |

### Node Maintenance
| Command | Description | Example |
|---------|-------------|---------|
| `kubectl cordon <node>` | Mark a node as unschedulable (no new pods will be scheduled there) | `kubectl cordon node-1` |
| `kubectl drain <node> --ignore-daemonsets --delete-emptydir-data` | Evict pods from a node safely for maintenance/upgrades | `kubectl drain node-1 --ignore-daemonsets --delete-emptydir-data` |
| `kubectl uncordon <node>` | Mark a node as schedulable again | `kubectl uncordon node-1` |

### Cluster Operations & Health
| Command | Description | Example |
|---------|-------------|---------|
| `kubectl cluster-info` | Display cluster endpoint information (control plane, CoreDNS, etc.) | `kubectl cluster-info` |
| `kubectl get nodes -o wide` | List all nodes with details like internal/external IP, OS, kernel, container runtime | `kubectl get nodes -o wide` |
| `kubectl api-resources` | List all supported API resources with their shortcodes, API groups, and namespaces | `kubectl api-resources` |
| `kubectl get csr` | List all Certificate Signing Requests | `kubectl get csr` |
| `kubectl certificate approve <name>` | Approve a pending Certificate Signing Request (CSR) | `kubectl certificate approve csr-abcde` |

### Backup Configuration
| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get all -A -o yaml > cluster-backup.yaml` | Export a snapshot of all standard resource configs in all namespaces | `kubectl get all -A -o yaml > cluster-backup.yaml` |

Feel free to extend this list with additional production operational commands.
