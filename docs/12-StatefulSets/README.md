# StatefulSets

A quick reference for common `kubectl` commands to manage StatefulSets (`sts`).

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get statefulsets` | List all StatefulSets in the current namespace | `kubectl get sts` |
| `kubectl get sts -n <namespace>` | List StatefulSets in a specific namespace | `kubectl get sts -n dev` |
| `kubectl describe sts <name>` | Detailed info about a specific StatefulSet | `kubectl describe sts db-cluster` |
| `kubectl scale sts <name> --replicas=<count>` | Scale a StatefulSet | `kubectl scale sts db-cluster --replicas=3` |
| `kubectl rollout status sts/<name>` | Check the status of a StatefulSet rollout | `kubectl rollout status sts/db-cluster` |
| `kubectl rollout history sts/<name>` | View rollout history/revisions of a StatefulSet | `kubectl rollout history sts/db-cluster` |
| `kubectl rollout undo sts/<name>` | Roll back a StatefulSet to the previous revision | `kubectl rollout undo sts/db-cluster` |
| `kubectl edit sts <name>` | Edit the configuration of a StatefulSet | `kubectl edit sts db-cluster` |
| `kubectl delete sts <name>` | Delete a StatefulSet (does not automatically delete associated PVCs) | `kubectl delete sts db-cluster` |
| `kubectl delete sts <name> --cascade=orphan` | Delete the StatefulSet controller but keep its pods running | `kubectl delete sts db-cluster --cascade=orphan` |

> [!NOTE]
> When you delete or scale down a StatefulSet, the associated Persistent Volume Claims (PVCs) are **not** automatically deleted. This is a safety feature to prevent accidental data loss. You must delete PVCs manually if they are no longer needed.

Feel free to extend this list with additional StatefulSet commands as needed.
