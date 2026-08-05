# Namespaces

A quick reference for common namespace‑related `kubectl` commands.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get namespaces` | List all namespaces | `kubectl get ns` |
| `kubectl create namespace <name>` | Create a new namespace | `kubectl create namespace dev` |
| `kubectl delete namespace <name>` | Delete a namespace | `kubectl delete namespace dev` |
| `kubectl config set-context --current --namespace=<name>` | Set default namespace for current context | `kubectl config set-context --current --namespace=dev` |
| `kubectl get all -n <name>` | Show all resources in a specific namespace | `kubectl get all -n dev` |
| `kubectl describe namespace <name>` | Detailed info about a namespace | `kubectl describe ns dev` |
| `kubectl label namespace <name> <key>=<value>` | Add a label to a namespace | `kubectl label namespace dev env=staging` |
| `kubectl annotate namespace <name> <key>=<value>` | Add an annotation to a namespace | `kubectl annotate namespace dev owner=team-a` |

Feel free to extend this list with additional commands as needed.
