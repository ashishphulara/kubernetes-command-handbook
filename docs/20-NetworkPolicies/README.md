# Network Policies

Network Policies (`netpol`) allow you to control traffic flow at the IP address or port level (OSI layer 3 or 4) for Pods in your cluster. Here is a reference of common commands for managing, inspecting, and troubleshooting Network Policies.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get netpol` | List all Network Policies in the current namespace | `kubectl get netpol` |
| `kubectl get netpol -A` | List all Network Policies across all namespaces | `kubectl get netpol -A` |
| `kubectl describe netpol <name>` | Inspect details of a Network Policy, including ingress/egress rules and selectors | `kubectl describe netpol allow-db-access` |
| `kubectl get netpol <name> -o yaml` | View the YAML definition of a specific Network Policy | `kubectl get netpol allow-db-access -o yaml` |
| `kubectl delete netpol <name>` | Delete a Network Policy | `kubectl delete netpol allow-db-access` |
| `kubectl apply -f <filename>.yaml` | Create or update a Network Policy from a file | `kubectl apply -f network-policy.yaml` |
| `kubectl explain netpol.spec` | Learn about the fields and options available in the Network Policy specification | `kubectl explain netpol.spec` |
| `kubectl get netpol -l <label>` | Filter Network Policies by label selector | `kubectl get netpol -l app=secure` |

Feel free to extend this list with additional commands for Network Policies.
