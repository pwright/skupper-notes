# Glossary

An explanation of common terms used with {skupper-name}.

* **{service-network}**\
A network of {skupper-name} sites linked together to share services.
* **service**\
In {skupper-name}, the Kubernetes [service](https://kubernetes.io/docs/concepts/services-networking/service/)  concept is extended to  allow communication with sites outside the cluster. 
When you define a service using Skupper, that service appears as a native service in other sites.
* **site**\
A {skupper-name} site is an {skupper-name} installation.
You _link_ sites to form a {service-network} and share services
* **link**\
A secure connection between sites that enables communication and service sharing between those sites.
* **gateway**\
A system service running on a Linux machine that enables you expose services, for example a database, on the {service-network}.
