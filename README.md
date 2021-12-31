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
###
###
