# CronJobs

A quick reference for common `kubectl` commands to manage CronJobs (`cj`).

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get cronjobs` | List all CronJobs in the current namespace | `kubectl get cj` |
| `kubectl get cj -n <namespace>` | List CronJobs in a specific namespace | `kubectl get cj -n dev` |
| `kubectl describe cj <name>` | Detailed info about a specific CronJob | `kubectl describe cj nightly-backup` |
| `kubectl create cronjob <name> --schedule="<cron-schedule>" --image=<image>` | Create a CronJob imperatively | `kubectl create cronjob my-cronjob --schedule="*/5 * * * *" --image=busybox` |
| `kubectl create job <job-name> --from=cronjob/<cronjob-name>` | Manually trigger/run a Job immediately from a CronJob | `kubectl create job manual-run --from=cronjob/nightly-backup` |
| `kubectl patch cj <name> -p '{"spec" : {"suspend" : true}}'` | Suspend/Pause execution of a CronJob | `kubectl patch cj nightly-backup -p '{"spec" : {"suspend" : true}}'` |
| `kubectl patch cj <name> -p '{"spec" : {"suspend" : false}}'` | Resume/Unpause a suspended CronJob | `kubectl patch cj nightly-backup -p '{"spec" : {"suspend" : false}}'` |
| `kubectl edit cj <name>` | Edit the configuration of a CronJob | `kubectl edit cj nightly-backup` |
| `kubectl delete cj <name>` | Delete a CronJob | `kubectl delete cj nightly-backup` |

Feel free to extend this list with additional CronJob commands as needed.
