# DaemonSets

A quick reference for common `kubectl` commands to manage DaemonSets (`ds`).

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get daemonsets` | List all DaemonSets in the current namespace | `kubectl get ds` |
| `kubectl get ds -n <namespace>` | List DaemonSets in a specific namespace | `kubectl get ds -n kube-system` |
| `kubectl describe ds <name>` | Detailed info about a specific DaemonSet | `kubectl describe ds fluentd-elasticsearch` |
| `kubectl set image ds/<name> <container>=<image>` | Update the image of a container in a DaemonSet | `kubectl set image ds/fluentd-elasticsearch fluentd=fluentd:v1.4` |
| `kubectl rollout status ds/<name>` | Check the status of a DaemonSet rollout | `kubectl rollout status ds/fluentd-elasticsearch` |
| `kubectl rollout history ds/<name>` | View rollout history/revisions of a DaemonSet | `kubectl rollout history ds/fluentd-elasticsearch` |
| `kubectl rollout undo ds/<name>` | Roll back a DaemonSet to the previous revision | `kubectl rollout undo ds/fluentd-elasticsearch` |
| `kubectl rollout restart ds/<name>` | Restart all pods managed by a DaemonSet | `kubectl rollout restart ds/fluentd-elasticsearch` |
| `kubectl edit ds <name>` | Edit the configuration of a DaemonSet | `kubectl edit ds fluentd-elasticsearch` |
| `kubectl delete ds <name>` | Delete a DaemonSet | `kubectl delete ds fluentd-elasticsearch` |

Feel free to extend this list with additional DaemonSet commands as needed.
