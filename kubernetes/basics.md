## Control Plane

The control plane acts as the brain of the operation, managing the worker nodes and the workloads running on them. Here are some key components:

#### API Server:
The central point of contact for Kubernetes. It receives requests to manage the cluster and translates them into instructions for the other components.

#### etcd: 
A distributed key-value store that holds the desired state of the cluster configuration. Think of it as the central storage for Kubernetes.

#### Scheduler: 
As the name suggests, this component decides which worker node is best suited to run a particular pod (a group of containers). It considers factors like resource availability, node health, and any specified preferences.

#### Controller Manager: 
This is a collection of controllers that constantly monitor the state of the cluster and take corrective actions to ensure it matches the desired state defined in the configuration.

## Worker Nodes

These are the workhorses of the cluster, the machines that actually run the containerized applications. Each node has several components:

#### Container Runtime Engine: 
Software like Docker or containerd that manages the lifecycle of containers on the node.

#### kubelet: 
The agent running on each node that communicates with the control plane. It receives instructions from the control plane, manages containers, and reports node health.

#### kube-proxy: 
This component on each node implements the Kubernetes networking model, allowing pods to communicate with each other across the cluster.

-----

There are many API resources in Kubernetes, and the specific ones available might depend on your cluster configuration and enabled API groups. However, here's a breakdown of the different categories and some common resources within each:

#### Workloads: 
These resources define how containerized applications run on your cluster:

##### Pods: 
The basic unit for deploying containerized applications. A pod can hold one or more containers that share storage and network resources.

##### Deployments: 
Manage the desired state of your pods. They ensure a specified number of pod replicas are running at all times and handle scaling and updates.

##### StatefulSets: 
Similar to deployments, but guarantee a unique and persistent identity for each pod replica. Used for applications requiring ordered scaling or that maintain state.

##### DaemonSets: 
Ensure exactly one or more pods run on each node in the cluster. Useful for background tasks or system services needed on all nodes.

##### Jobs: 
Run a pod to completion, often used for batch tasks or one-time jobs.

---

#### Discovery & Load Balancing: 
These resources expose your applications to external traffic:

##### Services: 
Act as an abstraction layer for pods, providing a stable network identity for your application. They route traffic to the underlying pods based on defined rules.

##### Endpoints: 
Represent a set of pods that implement a service. They track the current running pods that are part of the service.

---

#### Config & Storage: 
These resources manage configuration data and persistent storage for your applications:

##### ConfigMaps: 
Store key-value pairs of configuration data that can be injected into pods as environment variables or mounted volumes.

##### Secrets: 
Store sensitive information like passwords, tokens, or API keys securely in the cluster.

##### PersistentVolumes (PVs): 
Represent raw storage resources available to the cluster. These can be disks, cloud storage, or other types.

##### PersistentVolumeClaims (PVCs): 
Requests for storage by pods. Pods specify their storage requirements through PVCs, which are then bound to available PVs.

---

#### Cluster Resources: 
Define the overall configuration and state of the Kubernetes cluster:

##### Namespaces: 
Isolate resources by project or team. They provide a way to organize and control access to resources within the cluster.

##### Nodes: 
Represent worker machines in the Kubernetes cluster that run containerized applications.

##### ResourceQuotas: 
Set limits on resource consumption in a namespace, preventing runaway processes from consuming excessive resources.

##### ClusterRoles & ClusterRoleBindings: 
Manage cluster-wide authorization for users and service accounts.

---

#### Custom Resources (CRDs): 
These allow extension of the Kubernetes API for custom applications. They define new resource types specific to your needs.

---

More Ref - https://kubernetes.io/docs/reference/