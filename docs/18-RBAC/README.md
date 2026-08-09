# RBAC (Role-Based Access Control)

A quick reference for `kubectl` commands to manage ServiceAccounts, Roles, ClusterRoles, and RoleBindings.

| Command | Description | Example |
|---------|-------------|---------|
| `kubectl get serviceaccounts` | List ServiceAccounts | `kubectl get sa` |
| `kubectl create serviceaccount <name>` | Create a ServiceAccount | `kubectl create sa app-reader` |
| `kubectl create role <name> --verb=<verbs> --resource=<resources>` | Create a Role imperatively | `kubectl create role pod-reader --verb=get,list,watch --resource=pods` |
| `kubectl create clusterrole <name> --verb=<verbs> --resource=<resources>` | Create a ClusterRole imperatively | `kubectl create clusterrole node-reader --verb=get,list --resource=nodes` |
| `kubectl create rolebinding <name> --role=<role> --serviceaccount=<ns>:<sa>` | Bind a Role to a ServiceAccount | `kubectl create rolebinding read-pods-binding --role=pod-reader --serviceaccount=default:app-reader` |
| `kubectl create clusterrolebinding <name> --clusterrole=<cr> --user=<username>` | Bind a ClusterRole to a User | `kubectl create clusterrolebinding admin-binding --clusterrole=cluster-admin --user=admin-user` |
| `kubectl auth can-i <verb> <resource>` | Check if the current user can perform an action | `kubectl auth can-i create deployments` |
| `kubectl auth can-i <verb> <resource> --as=system:serviceaccount:<ns>:<sa>` | Check permissions on behalf of a ServiceAccount | `kubectl auth can-i get pods --as=system:serviceaccount:default:app-reader` |
| `kubectl auth can-i --list` | List all permissions allowed for the current context | `kubectl auth can-i --list` |

Feel free to extend this list with additional RBAC commands as needed.
