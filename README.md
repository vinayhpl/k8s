# k8s

# Kube Architechture

![image](https://github.com/user-attachments/assets/78a25a5b-a4dd-4972-bd9e-e300cf2db547)


# Worker node (Data Plane)

kubelet (kube-apiserver)   
Kube-proxy     
container run time      

# Kube Master (Control Plane)

## API Server
Its a communication component in Kube master or control plane which exposes REST API to communicate between control plane and data plane.

Other components which uses API server to communicate.

## In Control Plane
**kube-controller-manager** uses the API Server to monitor and update cluster state.

Examples of controllers that interact with the API Server:
   * Node Controller checks node health.   
   * Replication Controller ensures correct pod replicas.
   * Endpoints Controller manages service endpoints.

**kube-scheduler** 
* checks the unscheduled pods through API server.
* Picks the node for pod deploy and send back information to API server about node.

**etcd (Key-Value Store)** 
* API Server is the only component that directly interacts with etcd(because both exists on same plane) and Stores all cluster state data of pods, nodes, deployments, configs(as every communication happens through API Server).
    

+----------------------------------------------------+
|                     Control Plane                  |   
| -------------------------------------------------- |
|  API Server  |  Controller Manager |  Scheduler    |     
| -------------------------------------------------- |     
|  etcd (Cluster State Database)                     |     
+----------------------------------------------------+   

+----------------------------------------------------+
|                     Worker Nodes                   |
| -------------------------------------------------- |
|  Kubelet  |  Kube Proxy  |  Container Runtime      |
| -------------------------------------------------- |
|               Pod 1       Pod 2       Pod 3        |
|               |---|       |---|       |---|        |
|            (Containers) (Containers) (Containers)  |
+----------------------------------------------------+








