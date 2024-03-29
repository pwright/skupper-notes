# skupper expose

Expose a set of pods through a Skupper address

Expose a set of pods through a Skupper address

    skupper expose [deployment <name>|pods <selector>|statefulset <statefulsetname>|service <name>]  --[option]

address:: 
The Skupper address to expose
 (string)
enable-tls:: 
If specified, the service will be exposed over TLS (valid only for http2 protocol)
 (bool)
headless:: 
Expose through a headless service (valid only for a statefulset target)
 (bool)
port:: 
The ports to expose on
 (ints)
protocol:: 
The protocol to proxy (tcp, http, or http2) (default "tcp")
 (string)
proxy-cpu:: 
CPU request for router pods
 (string)
proxy-cpu-limit:: 
CPU limit for router pods
 (string)
proxy-memory:: 
Memory request for router pods
 (string)
proxy-memory-limit:: 
Memory limit for router pods
 (string)
proxy-node-selector:: 
Node selector to control placement of router pods
 (string)
proxy-pod-affinity:: 
Pod affinity label matches to control placement of router pods
 (string)
proxy-pod-antiaffinity:: 
Pod antiaffinity label matches to control placement of router pods
 (string)
publish-not-ready-addresses:: 
If specified, skupper will not wait for pods to be ready
 (bool)
target-port:: 
The ports to target on pods
 (strings)

* [skupper](skupper.adoc)	 -
