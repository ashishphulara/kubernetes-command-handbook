# ReplicaSets

A quick reference for common `kubectl` commands to manage ReplicaSets (`rs`).

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get replicasets` | List all ReplicaSets in the current namespace | `kubectl get rs` |
| `kubectl get rs -n <namespace>` | List ReplicaSets in a specific namespace | `kubectl get rs -n dev` |
| `kubectl describe rs <name>` | Detailed information about a specific ReplicaSet | `kubectl describe rs my-replicaset` |
| `kubectl scale rs <name> --replicas=<count>` | Scale a ReplicaSet up or down | `kubectl scale rs my-replicaset --replicas=5` |
| `kubectl edit rs <name>` | Edit the configuration of a ReplicaSet | `kubectl edit rs my-replicaset` |
| `kubectl delete rs <name>` | Delete a ReplicaSet (also deletes its managed pods) | `kubectl delete rs my-replicaset` |
| `kubectl delete rs <name> --cascade=orphan` | Delete the ReplicaSet but keep the pods running | `kubectl delete rs my-replicaset --cascade=orphan` |
| `kubectl get rs -o wide` | List ReplicaSets with extra details (e.g., container images, selectors) | `kubectl get rs -o wide` |

Feel free to extend this list with additional ReplicaSet commands as needed.
