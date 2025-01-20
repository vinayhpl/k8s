# k8s

# Kube Architechture

![image](https://github.com/user-attachments/assets/78a25a5b-a4dd-4972-bd9e-e300cf2db547)


# Worker node (Data Plane)

kubelet (kube-apiserver)
Kube-proxy   
container run time    

# Kube Master (Control Plane)

# API server
Its a communication component in Kube master or control plane which exposes REST API to communicate between control plane and data plane.

Other components that which uses API server to communicate.

# In Control Plane
kube-controller-manager uses the API Server to monitor and update cluster state.

Examples of controllers that interact with the API Server:
   * Node Controller (checks node health)
Replication Controller (ensures correct pod replicas)
Endpoints Controller (manages service endpoints)
scheduler    
etcd    
controller manager    
cloud controller manager    

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







