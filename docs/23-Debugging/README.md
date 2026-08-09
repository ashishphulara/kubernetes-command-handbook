# Debugging

Debugging is a vital part of managing Kubernetes applications. Here is a reference of essential commands for inspecting logs, executing commands inside containers, using ephemeral debug containers, copying files, and forwarding ports.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl logs <pod>` | Retrieve logs for a Pod | `kubectl logs my-pod` |
| `kubectl logs <pod> -c <container>` | Retrieve logs for a specific container in a multi-container Pod | `kubectl logs my-pod -c web-server` |
| `kubectl logs -f <pod>` | Stream live logs (follow) | `kubectl logs -f my-pod` |
| `kubectl logs <pod> --previous` | Retrieve logs from a previously crashed instance of a container | `kubectl logs my-pod --previous` |
| `kubectl describe pod <pod>` | Check pod status, configurations, limits, and events list for diagnostics | `kubectl describe pod my-pod` |
| `kubectl get events --sort-by='.metadata.creationTimestamp'` | List events in the current namespace sorted by their creation time | `kubectl get events --sort-by='.metadata.creationTimestamp'` |
| `kubectl exec -it <pod> -- /bin/sh` | Open an interactive terminal session inside a container | `kubectl exec -it my-pod -- /bin/sh` |
| `kubectl exec -it <pod> -c <container> -- /bin/bash` | Open an interactive terminal in a specific container of a Pod | `kubectl exec -it my-pod -c web-server -- /bin/bash` |
| `kubectl debug -it <pod> --image=<debug-image> --target=<container>` | Run an ephemeral container inside the Pod's namespace and share process namespace | `kubectl debug -it my-pod --image=busybox --target=app-container` |
| `kubectl port-forward <pod> <local-port>:<pod-port>` | Forward a local port to a port on the Pod | `kubectl port-forward my-pod 8080:80` |
| `kubectl cp <pod>:<remote-path> <local-path>` | Copy a file from a Pod container to your local machine | `kubectl cp my-pod:/var/log/app.log ./app.log` |
| `kubectl cp <local-path> <pod>:<remote-path>` | Copy a local file into a Pod container | `kubectl cp ./config.json my-pod:/app/config.json` |

Feel free to extend this list with additional debugging and troubleshooting commands.
