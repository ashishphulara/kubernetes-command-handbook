# Deployments

A quick reference for common `kubectl` commands to manage Deployments (`deploy`).

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get deployments` | List all Deployments in the current namespace | `kubectl get deploy` |
| `kubectl get deploy -n <namespace>` | List Deployments in a specific namespace | `kubectl get deploy -n dev` |
| `kubectl describe deployment <name>` | Detailed info about a specific Deployment | `kubectl describe deployment my-deploy` |
| `kubectl create deployment <name> --image=<image>` | Create a deployment imperatively | `kubectl create deployment web-app --image=nginx:alpine` |
| `kubectl scale deployment <name> --replicas=<count>` | Scale a Deployment | `kubectl scale deployment my-deploy --replicas=3` |
| `kubectl set image deployment/<name> <container>=<image>` | Update the container image | `kubectl set image deployment/web-app nginx=nginx:1.21` |
| `kubectl rollout status deployment/<name>` | Check the status of a rollout | `kubectl rollout status deployment/web-app` |
| `kubectl rollout history deployment/<name>` | View rollout history/revisions | `kubectl rollout history deployment/web-app` |
| `kubectl rollout undo deployment/<name>` | Roll back to the previous revision | `kubectl rollout undo deployment/web-app` |
| `kubectl rollout undo deployment/<name> --to-revision=<rev>` | Roll back to a specific revision | `kubectl rollout undo deployment/web-app --to-revision=2` |
| `kubectl rollout pause deployment/<name>` | Pause the rollout | `kubectl rollout pause deployment/web-app` |
| `kubectl rollout resume deployment/<name>` | Resume a paused rollout | `kubectl rollout resume deployment/web-app` |
| `kubectl rollout restart deployment/<name>` | Restart all pods managed by a Deployment | `kubectl rollout restart deployment/web-app` |
| `kubectl edit deployment <name>` | Edit the configuration of a Deployment | `kubectl edit deployment my-deploy` |
| `kubectl delete deployment <name>` | Delete a Deployment (and its pods) | `kubectl delete deployment my-deploy` |

Feel free to extend this list with additional Deployment commands as needed.
