# Ingress

A quick reference for common `kubectl` commands to manage Ingress resources (`ing`).

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get ingress` | List all Ingress resources in the current namespace | `kubectl get ing` |
| `kubectl get ing -n <namespace>` | List Ingress resources in a specific namespace | `kubectl get ing -n production` |
| `kubectl describe ing <name>` | Detailed info about a specific Ingress configuration | `kubectl describe ing web-ingress` |
| `kubectl create ingress <name> --rule="<host><path>=<service>:<port>"` | Create an Ingress resource imperatively | `kubectl create ingress web-ingress --rule="app.example.com/api*=web-service:8080"` |
| `kubectl edit ing <name>` | Edit the configuration of an Ingress | `kubectl edit ing web-ingress` |
| `kubectl delete ing <name>` | Delete an Ingress resource | `kubectl delete ing web-ingress` |

Feel free to extend this list with additional Ingress commands as needed.
