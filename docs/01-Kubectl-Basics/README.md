# Kubectl Basics

A quick reference for the most frequently used `kubectl` commands.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl version` | Show client and server version | `kubectl version --short` |
| `kubectl config view` | Display current kubeconfig | `kubectl config view` |
| `kubectl get <resource>` | List resources of a type | `kubectl get pods` |
| `kubectl describe <resource> <name>` | Detailed info about a resource | `kubectl describe pod my-pod` |
| `kubectl apply -f <file.yaml>` | Apply a manifest file | `kubectl apply -f deployment.yaml` |
| `kubectl delete -f <file.yaml>` | Delete resources defined in a file | `kubectl delete -f service.yaml` |
| `kubectl logs <pod>` | Show pod logs | `kubectl logs my-pod` |
| `kubectl exec -it <pod> -- /bin/sh` | Open a shell in a container | `kubectl exec -it my-pod -- sh` |
| `kubectl expose` | Expose a resource as a Service | `kubectl expose deployment nginx --port=80 --type=LoadBalancer` |
| `kubectl top pod` | Show resource usage of pods | `kubectl top pod` |

Feel free to extend this list with additional commands as needed.
