kubernetes
==========

**Orchestration Technology - convert isolation containers running on different hardware into a cluster**

Master Node:
-----------
Master Node componets

**1.Kube-API Server**
  
   It provides kubernetes API using Jason / Yaml over http, states of API objects are stored in etcd.
  
   Communicates with user
  
   RESTful API end-points
  
   Manifest yaml files are accepted by apiserver

**2.Kube-scheduler**

   It is a program on master node which performs the scheduling tasks like launching containers in worker nodes based on resource        availability
    
   Handle pod creation and management

   kube-scheduler match/assign nodes to pods using taints and tolerations
    
    
**3.Controll-Manager**

  Main Job of Controller manager is to monitor replication controllers and create pods to maintain desired state.

**4.etcd**

  It is a Key value pair data base. It stores configuration data of cluster and cluster state.
  
  Metadata about spec and status of cluster
  
  source-of-truth for cluster state

Work Node:
==========
Work Node componets

**1.Kubelet**

  It is an agent which runs on every worker node and it's listen to kubernetes master  and takes care of creating, starting, deleting containers

**2.Kube-proxy**

  It routes the traffic to appropriate containers based on ip address and port number of the incoming request. In other words we can say it is used for port translation.

**3.Container Engine**

   Container Runtime Interface Tight-coupling between Kubelet and Container Engine(Docker)
   
Kubernetes Objects
==================

**pod**

  Pod: Atomic unit of deployment in Kubernetes it Consists of 1 or more tightly coupled containers and Pod runs on node, which is
controlled by master. Kubernetes only knows about pods it Can not start container without a pod. 1 pod usually contains 1 container and Multi-container pods are possible too Such containers are tightly coupled.

**Namespace**

  Divide physical cluster into multiple virtual clusters
  
  Three pre-defined namespaces:
  
  •default: if none specified
 
  •kube-system: for internal kubernetes objects
  
  •kube-public: auto-readable by all users

  Name scopes: names need to be unique only inside a
namespace

 •Future version: namespace -> common access control

 •Don’t use namespaces for versioning

 •Just use labels instead
