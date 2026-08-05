# Pods

A quick reference for common pod‑related `kubectl` commands.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get pods` | List all pods in the current namespace | `kubectl get pods` |
| `kubectl get pods -n <namespace>` | List pods in a specific namespace | `kubectl get pods -n dev` |
| `kubectl describe pod <name>` | Detailed info about a pod | `kubectl describe pod my-pod` |
| `kubectl logs <pod>` | Show logs of a pod | `kubectl logs my-pod` |
| `kubectl logs <pod> -c <container>` | Show logs of a specific container in a pod | `kubectl logs my-pod -c sidecar` |
| `kubectl exec -it <pod> -- /bin/sh` | Open a shell in a pod container | `kubectl exec -it my-pod -- sh` |
| `kubectl exec -it <pod> -c <container> -- /bin/sh` | Exec into a specific container | `kubectl exec -it my-pod -c app -- sh` |
| `kubectl delete pod <name>` | Delete a pod | `kubectl delete pod my-pod` |
| `kubectl rollout restart deployment/<name>` | Restart pods of a deployment | `kubectl rollout restart deployment/nginx` |
| `kubectl top pod` | Show resource usage for pods | `kubectl top pod` |

Feel free to extend this list with additional pod commands as needed.
