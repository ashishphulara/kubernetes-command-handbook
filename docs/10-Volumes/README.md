# Volumes

In Kubernetes, volumes are defined within a Pod's specification. While there are no direct `kubectl get volumes` commands, here is a quick reference of command patterns to inspect, troubleshoot, and check mounts, storage, and volumes.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl describe pod <name>` | Inspect the pod events and volume definitions (e.g., mounts, sources) | `kubectl describe pod my-pod` |
| `kubectl get pod <name> -o jsonpath='{.spec.volumes}'` | List all volumes defined in a Pod | `kubectl get pod my-pod -o jsonpath='{.spec.volumes}'` |
| `kubectl get pod <name> -o jsonpath='{.spec.containers[*].volumeMounts}'` | List volume mount paths within the containers | `kubectl get pod my-pod -o jsonpath='{.spec.containers[*].volumeMounts}'` |
| `kubectl get pvc` | List Persistent Volume Claims (PVC) | `kubectl get pvc` |
| `kubectl get pv` | List Persistent Volumes (PV) | `kubectl get pv` |
| `kubectl get sc` | List Storage Classes | `kubectl get sc` |
| `kubectl exec -it <pod> -- df -h` | Check disk/volume space usage inside a pod container | `kubectl exec -it my-pod -- df -h` |
| `kubectl exec -it <pod> -- ls -la <mount-path>` | Verify files and permissions in a mounted volume | `kubectl exec -it my-pod -- ls -la /data` |

Feel free to extend this list with additional volume-related commands as needed.
