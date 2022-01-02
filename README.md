# Kubernetes:
Kubernetes is a portable, extensible open-source platform managing containerized workloads and services, also it facilitates both declarative configuration and automation the of containerized applications.

## Kubernetes Objects:
Kubernetes objects are persistent entities in the Kubernetes system. Kubernetes uses these entities to represent the state of your cluster. Specifically, they can describe:  
1.What containerized applications are running (and on which nodes)  
2.The resources available to those applications  
3.The policies around how those applications behave, such as restart policies, upgrades, and fault-tolerance  

### Pod  
A pod is a group of one or more containers. A container is an enclosed, self-contained execution process, much like a process in an operating system. Kubernetes uses pods to run your code and images in the cluster.  

Kubernetes works with Pods, rather than containers, so that containers in the same pod can be guaranteed to run on the same machine. Containers in the same pod share their networking infrastructure, storage resources, and lifecycle.  

### Deployment:  
A deployment is an object in Kubernetes that lets you manage a set of identical pods.  
Without a deployment, you’d need to create, update, and delete a bunch of pods manually.  
With a deployment, you declare a single object in a YAML file. This object is responsible for creating the pods, making sure they stay up to date, and ensuring there are enough of them running.  
You can also easily autoscale your applications using a Kubernetes deployment.  

### Sevices:  
A Service enables network access to a set of Pods in Kubernetes.  
Services select Pods based on their labels, when a network request is made to the service, it selects all Pods in the cluster matching the service's selector, chooses one of them, and forwards the network request to it.  

The type property in the Service's spec determines how the service is exposed to the network. It changes where a Service is able to be accessed from.The possible types are are below:  

**ClusterIP:** The default value exposes a service which is only accessible from within the Kubernetes cluster you can not make requests to your Pods from outside the cluster.  
**NodePort:** This makes the service accessible on a static port on each Node in the cluster. This means that the service can handle requests that originate from outside the cluster.  
**LoadBalancer:** The service becomes accessible externally through a cloud provider's load balancer functionality.  


### Object spec and status
Almost every Kubernetes object includes two nested object fields that govern the object's configuration:   
1.object spec  
2.object status.  

For objects that have a spec, you have to set this when you create the object, providing a description of the characteristics you want the resource to have: its desired state.  

The status describes the current state of the object, supplied and updated by the Kubernetes system and its components. The Kubernetes control plane continually and actively manages every object's actual state to match the desired state you supplied.  

### Describing a Kubernetes object
When you create an object in Kubernetes, you must provide the object spec that describes its desired state, as well as some basic information about the object (such as a name).   
When you use the Kubernetes API to create the object (either directly or via kubectl).  

Here's an example .yaml file that shows the required fields and object spec for a Kubernetes Deployment:

![image](https://user-images.githubusercontent.com/41946619/147801496-2ae31bad-ab17-46ca-ae91-49ee66cca5c3.png)

#### Required Fields  
In the .yaml file for the Kubernetes object you want to create, you'll need to set values for the following fields:  

**apiVersion** - Which version of the Kubernetes API you're using to create this object  
**kind** - What kind of object you want to create  
**metadata** - Data that helps uniquely identify the object, including a name string, UID, and optional namespace.  
**spec** - What state you desire for the object  

### Kubernetes Object Management  
The kubectl command-line tool supports several different ways to create and manage Kubernetes objects.  

#### Management technique
1. Imperative commands- Live Objects  
2. Imperative object configuration-Individual  fles  
3. Declarative object configuration- Directories of files  

### Namespaces  
In Kubernetes, namespaces provides a mechanism for isolating groups of resources within a single cluster.  

#### Kubernetes starts with four initial namespaces:  

**default** The default namespace for objects with no other namespace.  
**kube-system** The namespace for objects created by the Kubernetes system  
**kube-public** This namespace is created automatically and is readable by all users (including those not authenticated). This namespace is mostly reserved for cluster usage, in case that some resources should be visible and readable publicly throughout the whole cluster. The public aspect of this namespace is only a convention, not a requirement.  
**kube-node-lease** This namespace holds Lease objects associated with each node. Node leases allow the kubelet to send heartbeats so that the control plane can detect node failure.  

### Labels and Selectors  
Labels are key/value pairs that are attached to objects, such as pods. Labels are intended to be used to specify identifying attributes of objects that are meaningful and relevant to users, but do not directly imply semantics to the core system. Labels can be used to organize and to select subsets of objects.  
Labels can be attached to objects at creation time and subsequently added and modified at any time.  
Each object can have a set of key/value labels defined. Each Key must be unique for a given object.  
