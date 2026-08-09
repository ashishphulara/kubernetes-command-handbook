# Persistent Volumes

A quick reference for common `kubectl` commands to manage Persistent Volumes (`pv`), Persistent Volume Claims (`pvc`), and Storage Classes (`sc`).

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get pv` | List all Persistent Volumes in the cluster (PVs are cluster-wide) | `kubectl get pv` |
| `kubectl get pvc` | List all Persistent Volume Claims in the current namespace | `kubectl get pvc` |
| `kubectl get pvc -n <namespace>` | List PVCs in a specific namespace | `kubectl get pvc -n dev` |
| `kubectl get sc` | List Storage Classes in the cluster | `kubectl get sc` |
| `kubectl describe pv <name>` | Detailed info about a specific Persistent Volume | `kubectl describe pv my-pv` |
| `kubectl describe pvc <name>` | Detailed info about a specific Persistent Volume Claim | `kubectl describe pvc my-pvc` |
| `kubectl describe sc <name>` | Detailed info about a specific Storage Class | `kubectl describe sc standard` |
| `kubectl edit pv <name>` | Edit a Persistent Volume configuration | `kubectl edit pv my-pv` |
| `kubectl edit pvc <name>` | Edit a Persistent Volume Claim configuration | `kubectl edit pvc my-pvc` |
| `kubectl delete pvc <name>` | Delete a PVC (releases the bound PV, depending on reclaim policy) | `kubectl delete pvc my-pvc` |
| `kubectl delete pv <name>` | Delete a PV | `kubectl delete pv my-pv` |

Feel free to extend this list with additional storage and Persistent Volume commands as needed.
