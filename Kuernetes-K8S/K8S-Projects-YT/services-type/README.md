What is the role of a service in Kubernetes?
````
Kubernetes services connect a set of pods to an abstracted service name and IP address.
Services provide discovery and routing between pods.
For example, services connect an application front-end to its backend,
each of which running in separate deployments in a cluster.
````

What is a Kubernetes service vs pod?
````
Using a Service to Expose Your App | Kubernetes
A Service in Kubernetes is an abstraction which defines a logical set of Pods and a policy by which to access them.
Services enable a loose coupling between dependent Pods.
A Service is defined using YAML or JSON, like all Kubernetes object manifests.
````


What is service and ingress in Kubernetes?
````
Kubernetes Ingress Services Definition
In Kubernetes, an ingress is an API object that manages external IP access to services in a cluster,
typically exposing outside HTTP and HTTPS routes to services inside the cluster.
A set of rules the ingress resource defines controls traffic routing.
````
