# Kubernetes:
Kubernetes is a portable, extensible open-source platform managing containerized workloads and services, also it facilitates both declarative configuration and automation the of containerized applications.

## Kubernetes Objects:
Kubernetes objects are persistent entities in the Kubernetes system. Kubernetes uses these entities to represent the state of your cluster. Specifically, they can describe:  
1.What containerized applications are running (and on which nodes)  
2.The resources available to those applications  
3.The policies around how those applications behave, such as restart policies, upgrades, and fault-tolerance  
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

**metadata** - Data that helps uniquely identify the object, including a name string, UID, and optional namespace  

**spec** - What state you desire for the object  
