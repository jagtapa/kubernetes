# kubernetes Control Plane

The Control plane comprises the components that work together to control the different functioning of the kubernetes. It has api-server, cloud controller manager, controller manager, kube scheduler and etcd. Let’s talk about each component and what are their tasks.What is a control plane in Kubernetes? Basics on Kubernetes.

**Kube-apiserver** : Kube-apiserver exposes the Kubernetes APIs and is responsible for saving and updating the states in etcd. It is a kind of outer world interface of kubernetes. Anyone who wants to make changes in Kubernetes interacts with kube-apiserver.

**Cloud controller manager** : This is the component that handles the cloud-specific logic. Now what this means is if you have asked for some component in k8s, it may be implemented in different ways in different clouds. Cloud controller manager understands this and creates the resources as per cloud. You can simply understand this as kubernetes resources to cloud resources mapping or how a particular resource will be implemented in different clouds.
Cloud controller manager runs only if you are running k8s on any cloud. If you are running Kubernetes on your premise, you will not need a cloud controller manager.

**etcd**: etcd is a persistent store for Kubernetes store. It is a highly consistent and available key-value datastore. 
etcd is well protected in Kubernetes and only Kube API server can talk to it. Any other component that wants to interact with etcd has to do through API server.


**controller manager**: These are the controller to handle the basic functionality of Kubernetes like node management, job management, endpoint management, service and account token controllers, and other such components.
So in short this is the process that takes over when a node joins, a new endpoint is created, a new service account is created and other basic functionality of Kubernetes.Kube-

**scheduler** :The main task of this is to find out the pods which are not assigned any node and assign a node to them. This includes the factors involved in node selection like affinity, anti-affinity etc.




------------------------------------
**on Worker Node**

**Kube-proxy**
The main task of Kube-proxy is making configurations so that packets can reach their destination when you call a service and not routing the packets. 
This must be clear to you, in the very basic configuration, when you talk about kube-proxy it doesn’t route the packets, it makes configuration so that packet can reach the destination.
What configuration does it make?
-> Kube-proxy creates iptables rules for the services that are created.
-> Kube proxy runs on each node and talks to api-server to get the details of the services and endpoints present. Based on this information, kube-proxy creates entries in iptables, which then routes the packets to the correct destination.
-> When you create any service in Kubernetes, the traffic can come on any of the nodes, and then its iptables will route the packet to the correct node and after that, it can reach the correct pod.
