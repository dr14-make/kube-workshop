# Namespaces

* In Kubernetes, namespaces provide a mechanism for isolating groups of resources within a single cluster.

* Names of resources need to be unique within a namespace, but not across namespaces.

* There are two types of objects:
    * Namespaced objects
        * Deployments
        * Services
        * ...
    * Cluster-wide objects
        * StorageClass
        * PersistentVolumes
        * ...

Namespace-based scoping is applicable only for namespaced objects.


```
kubectl get namespace
```

# Pods

Pods are the smallest deployable units of computing that you can create and manage in Kubernetes.

# Services

In Kubernetes, a Service is a method for exposing a network application that is running as one or more Pods in your cluster.

When you create a Service, it creates a corresponding DNS entry. This entry is of the form <service-name>.<namespace-name>.svc.cluster.local

Different types:

 * ClusterIp
    - Exposes the Service on a cluster-internal IP. Choosing this value makes the Service only reachable from within the cluster
 * NodePort
    - Exposes the Service on each Node's IP at a static port
 * LoadBalancer
    - Exposes the Service externally using an external load balancer (Needs a provider)
 * ExternalName (Rearly used)
    - Maps the Service to the contents of the externalName field

# ReplicaSet

A ReplicaSet's purpose is to maintain a stable set of replica Pods running at any given time. As such, it is often used to guarantee the availability of a specified number of identical Pods.


# Deployment

A Deployment is the preferred way to deploy an application inside a pod. It is a higher-level abstraction built on top of ReplicaSets that uses ReplicaSets internally to manage applications. In addition to the work carried out by a ReplicaSet, it provides added functionality such as

* Rolling Updates: Rolling updates ensure that an application is updated gradually, one replica at a time, while ensuring that the overall availability of the application is not impacted. In comparison, ReplicaSets only support scaling and managing replicas.

* Rollback: Deployments automatically rollback to a previous version of an application if an update fails. For ReplicaSets, this process would need to be manually performed.

* Version Control: Similar to the previous feature, Deployments implement version control, hence allowing for the ability to rollback to a previous specific version.


# StatefulSet

StatefulSet is the controller that manages the deployment and scaling of a set of Stateful pods. A stateful pod in Kubernetes is a pod that requires persistent storage and a stable network identity to maintain its state all the time, even during pod restarts or rescheduling. These pods are commonly used for stateful applications such as databases or distributed file systems as these require a stable identity and persistent storage to maintain data consistency.

# Environments and secrets