# Services

A quick reference for common `kubectl` commands to manage Services (`svc`).

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get services` | List all Services in the current namespace | `kubectl get svc` |
| `kubectl get svc -n <namespace>` | List Services in a specific namespace | `kubectl get svc -n dev` |
| `kubectl describe svc <name>` | Detailed info about a specific Service | `kubectl describe svc my-service` |
| `kubectl expose deployment <name> --port=<port> --target-port=<target-port>` | Expose a Deployment as a Service (ClusterIP by default) | `kubectl expose deployment web-app --port=80 --target-port=8080` |
| `kubectl expose deployment <name> --port=<port> --type=NodePort` | Expose a Deployment as a NodePort Service | `kubectl expose deployment web-app --port=80 --type=NodePort` |
| `kubectl expose deployment <name> --port=<port> --type=LoadBalancer` | Expose a Deployment as a LoadBalancer Service | `kubectl expose deployment web-app --port=80 --type=LoadBalancer` |
| `kubectl create service clusterip <name> --tcp=<port>:<target-port>` | Create a ClusterIP Service imperatively | `kubectl create service clusterip my-cip --tcp=80:8080` |
| `kubectl create service nodeport <name> --tcp=<port>:<target-port>` | Create a NodePort Service imperatively | `kubectl create service nodeport my-np --tcp=80:8080` |
| `kubectl create service loadbalancer <name> --tcp=<port>:<target-port>` | Create a LoadBalancer Service imperatively | `kubectl create service loadbalancer my-lb --tcp=80:8080` |
| `kubectl get endpoints <service-name>` | List endpoints associated with a Service | `kubectl get ep my-service` |
| `kubectl edit svc <name>` | Edit the configuration of a Service | `kubectl edit svc my-service` |
| `kubectl delete svc <name>` | Delete a Service | `kubectl delete svc my-service` |

Feel free to extend this list with additional Service commands as needed.
