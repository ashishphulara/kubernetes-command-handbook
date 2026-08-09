# Scheduling

A quick reference for `kubectl` commands related to node scheduling, taints, tolerations, cordoning, and draining nodes.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get nodes --show-labels` | List nodes in the cluster with all their labels | `kubectl get nodes --show-labels` |
| `kubectl label nodes <node-name> <key>=<value>` | Label a node (used for nodeSelector and NodeAffinity) | `kubectl label nodes worker-node-1 disktype=ssd` |
| `kubectl label nodes <node-name> <key>-` | Remove a label from a node | `kubectl label nodes worker-node-1 disktype-` |
| `kubectl taint nodes <node-name> <key>=<value>:<effect>` | Add a taint to a node (effects: `NoSchedule`, `PreferNoSchedule`, `NoExecute`) | `kubectl taint nodes worker-node-1 dedicated=special-user:NoSchedule` |
| `kubectl taint nodes <node-name> <key>:<effect>-` | Remove a taint from a node | `kubectl taint nodes worker-node-1 dedicated:NoSchedule-` |
| `kubectl cordon <node-name>` | Mark a node as unschedulable (prevents new pods from being scheduled) | `kubectl cordon worker-node-1` |
| `kubectl uncordon <node-name>` | Mark a node as schedulable (allows new pods to be scheduled) | `kubectl uncordon worker-node-1` |
| `kubectl drain <node-name> --ignore-daemonsets --delete-emptydir-data` | Evacuate pods from a node for maintenance | `kubectl drain worker-node-1 --ignore-daemonsets --delete-emptydir-data` |

Feel free to extend this list with additional scheduling commands as needed.
