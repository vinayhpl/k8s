# k8s

# Kube Architechture

![image](https://github.com/user-attachments/assets/78a25a5b-a4dd-4972-bd9e-e300cf2db547)


# Worker node (Data Plane)

kubelet (kube-apiserver)
component that integrates between master and data plane
Kube-proxy   
container run time    

# Kube Master (Control Plane)

API server 
Its a heart of kubernetes communication in control plane or kube master 
sceduler    
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
