# Secrets

A quick reference for common `kubectl` commands to manage Secrets.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get secrets` | List all Secrets in the current namespace | `kubectl get secrets` |
| `kubectl get secrets -n <namespace>` | List Secrets in a specific namespace | `kubectl get secrets -n dev` |
| `kubectl describe secret <name>` | Detailed info about a specific Secret (keys are shown, values are hidden) | `kubectl describe secret my-secret` |
| `kubectl create secret generic <name> --from-literal=<key>=<val>` | Create a generic secret from a literal value | `kubectl create secret generic db-secret --from-literal=password=P@ssw0rd` |
| `kubectl create secret generic <name> --from-file=<file-path>` | Create a generic secret from a file | `kubectl create secret generic ssh-key --from-file=~/.ssh/id_rsa` |
| `kubectl create secret generic <name> --from-env-file=<env-file>` | Create a generic secret from an env-file | `kubectl create secret generic app-secret --from-env-file=.env` |
| `kubectl create secret tls <name> --cert=<cert-file> --key=<key-file>` | Create a TLS secret (for SSL certificates) | `kubectl create secret tls my-tls --cert=tls.crt --key=tls.key` |
| `kubectl create secret docker-registry <name> --docker-server=<srv> --docker-username=<user> --docker-password=<pass>` | Create a Docker registry credential secret | `kubectl create secret docker-registry regcred --docker-server=https://index.docker.io/v1/ --docker-username=user --docker-password=pass` |
| `kubectl get secret <name> -o yaml` | View a secret in YAML format (values are base64 encoded) | `kubectl get secret db-secret -o yaml` |
| `kubectl get secret <name> -o jsonpath='{.data.<key>}' \| base64 --decode` | Decode a specific secret key value | `kubectl get secret db-secret -o jsonpath='{.data.password}' \| base64 --decode` |
| `kubectl edit secret <name>` | Edit the configuration of a Secret | `kubectl edit secret my-secret` |
| `kubectl delete secret <name>` | Delete a Secret | `kubectl delete secret my-secret` |

Feel free to extend this list with additional Secret commands as needed.
