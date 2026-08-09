# JSONPath

JSONPath template expressions are used to filter, format, and extract specific fields from the JSON outputs of `kubectl` commands using the `-o jsonpath="..."` flag. Here is a reference of common JSONPath query patterns.

| Query Pattern / Goal | Command Example |
|----------------------|-----------------|
| **List Pod Names** | `kubectl get pods -o jsonpath='{.items[*].metadata.name}'` |
| **List Pod Names with Newlines** | `kubectl get pods -o jsonpath='{range .items[*]}{.metadata.name}{"\n"}{end}'` |
| **Get Container Images for Pods** | `kubectl get pods -o jsonpath='{.items[*].spec.containers[*].image}'` |
| **Get Pod Name and Status** | `kubectl get pods -o jsonpath='{range .items[*]}{.metadata.name}{"\t"}{.status.phase}{"\n"}{end}'` |
| **List Node Internal IP Addresses** | `kubectl get nodes -o jsonpath='{.items[*].status.addresses[?(@.type=="InternalIP")].address}'` |
| **Get Pod IP Addresses** | `kubectl get pods -o jsonpath='{.items[*].status.podIP}'` |
| **Get ClusterIP of a Service** | `kubectl get svc -o jsonpath='{.items[*].spec.clusterIP}'` |
| **Decode Secret Data Value** | `kubectl get secret my-secret -o jsonpath='{.data.password}'` (Output needs base64 decoding) |
| **Get CPU Capacity of Nodes** | `kubectl get nodes -o jsonpath='{.items[*].status.capacity.cpu}'` |
| **List Port Configurations of Pods** | `kubectl get pods -o jsonpath='{.items[*].spec.containers[*].ports[*].containerPort}'` |
| **Find Restarts for all Pods** | `kubectl get pods -o jsonpath='{range .items[*]}{.metadata.name}{"\t"}{.status.containerStatuses[*].restartCount}{"\n"}{end}'` |

### Key Syntax Reminders
* `.` starts the root object.
* `..` is a deep scan operator.
* `*` wildcards all elements in a list.
* `[index]` accesses a specific list element (e.g. `[0]`).
* `[?(@.type=="Value")]` filters elements based on a nested condition.
* `{range ...}...{end}` loops through arrays to format output cleanly.
* `{"\n"}` and `{"\t"}` insert newlines and tabs.

Feel free to extend this list with additional JSONPath formatting examples.
