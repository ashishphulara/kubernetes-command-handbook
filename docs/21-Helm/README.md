# Helm

Helm is the package manager for Kubernetes. It helps you manage Kubernetes applications through Helm Charts. Here is a reference of common Helm commands for repo management, release lifecycle, package creation, and troubleshooting.

| Command | Description | Example |
|---------|-------------|---------|
| `helm repo add <name> <url>` | Add a chart repository | `helm repo add bitnami https://charts.bitnami.com/bitnami` |
| `helm repo update` | Update information of available charts from chart repositories | `helm repo update` |
| `helm search repo <keyword>` | Search repositories for a keyword | `helm search repo nginx` |
| `helm install <release> <chart>` | Install a helm chart with a release name | `helm install my-nginx bitnami/nginx` |
| `helm list` | List releases in the current namespace (use `-A` for all namespaces) | `helm list` |
| `helm status <release>` | Show the status and details of a named release | `helm status my-nginx` |
| `helm show values <chart>` | Inspect the default configuration values (`values.yaml`) of a chart | `helm show values bitnami/nginx` |
| `helm get values <release>` | Retrieve the user-supplied values for a running release | `helm get values my-nginx` |
| `helm upgrade <release> <chart>` | Upgrade an existing release to a new version or apply updated values | `helm upgrade my-nginx bitnami/nginx --set service.type=NodePort` |
| `helm rollback <release> <revision>` | Roll back a release to a previous revision number | `helm rollback my-nginx 1` |
| `helm uninstall <release>` | Uninstall/delete a running release | `helm uninstall my-nginx` |
| `helm create <chart-name>` | Create a template directory structure for writing a new Helm Chart | `helm create my-custom-chart` |
| `helm lint <chart-path>` | Run linting checks on a local chart directory to find potential errors | `helm lint ./my-custom-chart` |
| `helm template <release> <chart-path>` | Locally render the templates to verify output manifests without installing | `helm template test-release ./my-custom-chart` |

Feel free to extend this list with additional Helm commands.
