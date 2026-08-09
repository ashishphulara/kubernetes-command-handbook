# Jobs

A quick reference for common `kubectl` commands to manage Jobs.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get jobs` | List all Jobs in the current namespace | `kubectl get jobs` |
| `kubectl get jobs -n <namespace>` | List Jobs in a specific namespace | `kubectl get jobs -n dev` |
| `kubectl describe job <name>` | Detailed info about a specific Job | `kubectl describe job my-job` |
| `kubectl create job <name> --image=<image>` | Create a Job imperatively | `kubectl create job my-job --image=perl:5.34.0` |
| `kubectl create job <job-name> --from=cronjob/<cronjob-name>` | Manually trigger/run a Job from an existing CronJob | `kubectl create job manual-run --from=cronjob/nightly-backup` |
| `kubectl logs -l job-name=<job-name>` | Stream/get logs from all pods associated with a Job | `kubectl logs -l job-name=my-job` |
| `kubectl edit job <name>` | Edit the configuration of a Job | `kubectl edit job my-job` |
| `kubectl delete job <name>` | Delete a Job (this will also delete the pods created by the Job) | `kubectl delete job my-job` |

Feel free to extend this list with additional Job commands as needed.
