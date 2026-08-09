# ConfigMaps

A quick reference for common `kubectl` commands to manage ConfigMaps (`cm`).

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get configmaps` | List all ConfigMaps in the current namespace | `kubectl get cm` |
| `kubectl get cm -n <namespace>` | List ConfigMaps in a specific namespace | `kubectl get cm -n dev` |
| `kubectl describe cm <name>` | Detailed info about a specific ConfigMap | `kubectl describe cm my-config` |
| `kubectl create cm <name> --from-literal=<key>=<value>` | Create a ConfigMap from a literal key-value pair | `kubectl create cm my-config --from-literal=APP_COLOR=blue` |
| `kubectl create cm <name> --from-file=<file-path>` | Create a ConfigMap from the contents of a file | `kubectl create cm my-config --from-file=config.properties` |
| `kubectl create cm <name> --from-file=<dir-path>` | Create a ConfigMap from all files in a directory | `kubectl create cm my-config --from-file=./configs/` |
| `kubectl create cm <name> --from-env-file=<env-file>` | Create a ConfigMap from an environment file | `kubectl create cm my-config --from-env-file=.env` |
| `kubectl get cm <name> -o yaml` | View the YAML definition and data of a ConfigMap | `kubectl get cm my-config -o yaml` |
| `kubectl edit cm <name>` | Edit the configuration of a ConfigMap | `kubectl edit cm my-config` |
| `kubectl delete cm <name>` | Delete a ConfigMap | `kubectl delete cm my-config` |

Feel free to extend this list with additional ConfigMap commands as needed.
