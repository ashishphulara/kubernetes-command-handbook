# Autoscaling

Kubernetes supports automatic scaling of workloads via Horizontal Pod Autoscaler (HPA), Vertical Pod Autoscaler (VPA), and Cluster Autoscaler. Here is a reference of common commands to configure, manage, and monitor autoscaling.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl autoscale deployment <name> --min=<min> --max=<max> --cpu-percent=<target>` | Create a HorizontalPodAutoscaler (HPA) targeting CPU utilization | `kubectl autoscale deployment my-app --min=2 --max=10 --cpu-percent=80` |
| `kubectl get hpa` | List Horizontal Pod Autoscalers in the current namespace | `kubectl get hpa` |
| `kubectl describe hpa <name>` | View detailed status of an HPA, including target metrics, current metrics, and scaling events | `kubectl describe hpa my-app` |
| `kubectl get hpa <name> -o yaml` | View the YAML configuration and full status of an HPA | `kubectl get hpa my-app -o yaml` |
| `kubectl delete hpa <name>` | Delete a Horizontal Pod Autoscaler | `kubectl delete hpa my-app` |
| `kubectl top nodes` | Display CPU and memory utilization of nodes (requires Metrics Server) | `kubectl top nodes` |
| `kubectl top pods` | Display CPU and memory utilization of pods (requires Metrics Server) | `kubectl top pods` |
| `kubectl get vpa` | List Vertical Pod Autoscalers (requires VPA controller installed) | `kubectl get vpa` |
| `kubectl describe vpa <name>` | Inspect VPA status, recommended resource requests, and current resource usage | `kubectl describe vpa my-app-vpa` |
| `kubectl explain hpa.spec` | Explore fields and options for the HorizontalPodAutoscaler API resource | `kubectl explain hpa.spec` |

Feel free to extend this list with additional Autoscaling commands.
