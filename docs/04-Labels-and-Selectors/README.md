# Labels and Selectors

A quick reference for `kubectl` commands used to manage labels and filter resources using selectors.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get <resource> --show-labels` | List resources and show all their labels | `kubectl get pods --show-labels` |
| `kubectl get <resource> -l <key>=<value>` | Filter resources by a specific label (equality-based) | `kubectl get pods -l env=production` |
| `kubectl get <resource> -l '<key> in (<val1>, <val2>)'` | Filter resources using set-based selector (in) | `kubectl get pods -l 'env in (production, qa)'` |
| `kubectl get <resource> -l '<key> notin (<val1>)'` | Filter resources using set-based selector (notin) | `kubectl get pods -l 'env notin (development)'` |
| `kubectl get <resource> -l <key>` | Filter resources where label key exists | `kubectl get pods -l env` |
| `kubectl get <resource> -l '!<key>'` | Filter resources where label key does not exist | `kubectl get pods -l '!env'` |
| `kubectl label <resource> <name> <key>=<value>` | Add a label to a specific resource | `kubectl label pod my-pod env=production` |
| `kubectl label <resource> <name> <key>=<value> --overwrite` | Update/overwrite an existing label | `kubectl label pod my-pod env=development --overwrite` |
| `kubectl label <resource> <name> <key>-` | Remove a label from a resource | `kubectl label pod my-pod env-` |
| `kubectl label <resource> --all <key>=<value>` | Add a label to all resources of a type in the namespace | `kubectl label pods --all tier=frontend` |

Feel free to extend this list with additional label and selector commands as needed.
