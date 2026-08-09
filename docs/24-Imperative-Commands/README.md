# Imperative Commands

Imperative commands allow you to quickly create, modify, and delete Kubernetes resources directly using `kubectl` flags instead of writing declarative YAML files first. They are also incredibly useful for generating YAML templates using `--dry-run=client -o yaml`.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl run <pod-name> --image=<image> --dry-run=client -o yaml` | Generate a Pod YAML template without creating it | `kubectl run nginx-pod --image=nginx --dry-run=client -o yaml` |
| `kubectl create deployment <name> --image=<image> --replicas=<num>` | Create a Deployment with specified replicas | `kubectl create deployment web-app --image=nginx --replicas=3` |
| `kubectl expose deployment <name> --port=<port> --target-port=<target> --type=<type>` | Expose a deployment as a Kubernetes Service | `kubectl expose deployment web-app --port=80 --target-port=80 --type=ClusterIP --name=web-service` |
| `kubectl create service <type> <name> --tcp=<port>:<target-port>` | Create a Service of a specific type (e.g. ClusterIP, NodePort, LoadBalancer) | `kubectl create service nodeport my-svc --tcp=80:8080` |
| `kubectl create namespace <name>` | Create a namespace | `kubectl create namespace dev-env` |
| `kubectl create configmap <name> --from-literal=key=value` | Create a ConfigMap from literal key-value pairs | `kubectl create configmap app-config --from-literal=db.host=localhost --from-literal=db.port=5432` |
| `kubectl create secret generic <name> --from-literal=key=value` | Create a Secret from literal key-value pairs | `kubectl create secret generic app-secret --from-literal=api.key=SuperSecretToken` |
| `kubectl create job <name> --image=<image> -- <command>` | Create a Job to run a single task | `kubectl create job one-time-task --image=busybox -- sleep 10` |
| `kubectl create cronjob <name> --image=<image> --schedule="<cron>" -- <command>` | Create a CronJob | `kubectl create cronjob recurring-task --image=busybox --schedule="0 * * * *" -- echo "Hourly check"` |
| `kubectl create ingress <name> --rule="<host><path>=<service>:<port>"` | Create an Ingress resource with routing rules | `kubectl create ingress web-ingress --rule="example.com/=web-service:80"` |
| `kubectl create role <name> --verb=<verbs> --resource=<resources>` | Create an RBAC Role | `kubectl create role pod-reader --verb=get,list,watch --resource=pods` |
| `kubectl create rolebinding <name> --role=<role> --user=<username>` | Bind a Role to a user/group/serviceaccount | `kubectl create rolebinding read-pods --role=pod-reader --user=john` |

Feel free to extend this list with additional imperative commands.
