# Probes

In Kubernetes, probes (Liveness, Readiness, and Startup) are defined inside the container spec of a Pod. While there is no direct `kubectl get probes` command, here is a reference of command patterns to inspect, monitor, and troubleshoot probes.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl describe pod <name>` | Inspect pod events and probe configuration details (e.g., HTTP path, port, timeouts, failure thresholds). Look here to diagnose health check failures. | `kubectl describe pod my-pod` |
| `kubectl get pod <name> -o jsonpath='{.spec.containers[*].livenessProbe}'` | View the Liveness Probe configuration for a pod's containers | `kubectl get pod my-pod -o jsonpath='{.spec.containers[*].livenessProbe}'` |
| `kubectl get pod <name> -o jsonpath='{.spec.containers[*].readinessProbe}'` | View the Readiness Probe configuration for a pod's containers | `kubectl get pod my-pod -o jsonpath='{.spec.containers[*].readinessProbe}'` |
| `kubectl get pod <name> -o jsonpath='{.spec.containers[*].startupProbe}'` | View the Startup Probe configuration for a pod's containers | `kubectl get pod my-pod -o jsonpath='{.spec.containers[*].startupProbe}'` |
| `kubectl get pods -w` | Watch pods to see if they are running but not ready (e.g., `0/1` Ready), which often indicates readiness probe failure | `kubectl get pods -w` |
| `kubectl get pods -o custom-columns=NAME:.metadata.name,RESTARTS:.status.containerStatuses[*].restartCount` | List pods and their restart counts (frequent restarts are typically caused by liveness probe failures) | `kubectl get pods -o custom-columns=NAME:.metadata.name,RESTARTS:.status.containerStatuses[*].restartCount` |
| `kubectl logs <pod> --previous` | Check logs from the previous instance of a container before it crashed/restarted due to a failed liveness probe | `kubectl logs my-pod --previous` |

Feel free to extend this list with additional debugging and troubleshooting commands for probes.
