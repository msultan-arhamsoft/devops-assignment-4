# Assignment # 4, Submitted by Mahmood Sultan #

## Kubernetes (k8s) Architecture ##

### Kubernetes - Key Concepts ###
- Deployments made through Kubernetes results in cluster. 
- A Kubernetes cluster consists of nodes.
- Nodes run containerized applications.
- Every cluster has at least one worker node.
- Worker nodes host the Pods.
- Pods are components of application workload.
- The control plane manages the worker nodes and the Pods in the cluster.
- In production environments, the control plane usually runs across multiple computers and a cluster usually runs multiple nodes, providing fault-tolerance and high availability.


### Components of Kubernetes ###
There are 3 major types of components of Kubernetes cluster:
1- Control Plane Components
2- Node Components
3- Addons

#### Control Plane Components ####
- The Control plane's components are responsible for:
- - Making decisions about the cluster.
- - Detecting cluster events.
- - Responding to cluster events.
- - All the component of control plane can be run on the on any machine on the cluster.
- - By default, all the control plane components run on the same machine, and the other containers are not run on that machine.

##### The control planes components are as follows #####

###### API Server ######
- The component, that exposes the k8s API, is called the The API server.
- API Server is the front end for the Kubernetes control plane.
- Main implementation of the k8s API server is kube-apiserve.

###### etcd ######
- The is the key value based store/database for storing the k8s clusters data.

###### Scheduler ######
- The component that is responsible for watching and asigning the nodes to the pods, is called the scheduler.
- The scheduler assings the nodes to pods based on different factors like: hardware, software, deadlines, policies etc.
- Main implementation of the k8s Scheduler is kube-scheduler.

###### Controller Manager ######
- The control plane's component that manages controller processes.
- Some types of Controller in k8s are:
- - Node Controllers
- - Service Controller
- - Ingress Controllers
- - Replication Controllers
- - Endpoints Controllers

#### Node Components ####
- The node components are the component that run on every node and are responsible to maintain the running pods.
- The node componnets provide the k8s run time environments.

##### The Node components are as follows #####

###### kubelet ######
- kubelet runs on every node in the cluster.
- kubelet makes sure that containers are running in a pod.
- kubelet makes sure that the containers are running and healthy.
- kubelet only manages the containers that were created by the k8s.

###### kube-proxy ######
- kube-proxy is the network-proxy that maintains network rules on each node.
- The network rules define the access/restrictions for the communications inside and outside the cluster.
- Like other Node components kube-proxy also runs on every node in the cluster.

###### Container runtime ######
- k8s supports container runtimes such as containerd, CRI-O.
- Container runtime is the software that is responsibe for running containers.


#### Addons ####
- The third kind of componnets are addons which k8s supports.
- Addons use k8s resources to implement cluster features.
- There are many Addons components like DNS, Web UI, Container Resource Monitoring, Cluster-level logging, etc.