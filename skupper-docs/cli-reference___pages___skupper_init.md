# skupper init

Initialise skupper installation

Setup a router and other supporting objects to provide a functional skupper installation that can then be connected to other skupper installations

    skupper init  --[option]

site-name:: 
Provide a specific name for this skupper installation
 (string)
ingress:: 
Setup Skupper ingress to one of: [route|loadbalancer|nodeport|nginx-ingress-v1|contour-http-proxy|ingress|none]. If not specified route is used when available, otherwise loadbalancer is used.
 (string)
ingress-host:: 
Hostname or alias by which the ingress route or proxy can be reached
 (string)
router-mode:: 
Skupper router-mode (default "interior")
 (string)
labels:: 
Labels to add to skupper pods
 (strings)
router-logging:: 
Logging settings for router. 'trace', 'debug', 'info' (default), 'notice', 'warning', and 'error' are valid values.
 (string)
router-debug-mode:: 
Enable debug mode for router ('asan' or 'gdb' are valid values)
 (string)
routers:: 
Number of router replicas to start
 (int)
enable-console:: 
Enable skupper console (default true)
 (bool)
create-network-policy:: 
Create network policy to restrict access to skupper services exposed through this site to current pods in namespace
 (bool)
console-auth:: 
Authentication mode for console(s). One of: 'openshift', 'internal', 'unsecured'
 (string)
console-user:: 
Skupper console user. Valid only when --console-auth=internal
 (string)
console-password:: 
Skupper console user. Valid only when --console-auth=internal
 (string)
console-ingress:: 
Determines if/how console is exposed outside cluster. If not specified uses value of --ingress. One of: [route|loadbalancer|nodeport|nginx-ingress-v1|contour-http-proxy|ingress|none].
 (string)
ingress-annotations:: 
Annotations to add to skupper ingress
 (strings)
annotations:: 
Annotations to add to skupper pods
 (strings)
router-service-annotations:: 
Annotations to add to skupper router service
 (strings)
controller-service-annotation:: 
Annotations to add to skupper controller service
 (strings)
enable-service-sync:: 
Participate in cross-site service synchronization (default true)
 (bool)
router-cpu:: 
CPU request for router pods
 (string)
router-memory:: 
Memory request for router pods
 (string)
router-cpu-limit:: 
CPU limit for router pods
 (string)
router-memory-limit:: 
Memory limit for router pods
 (string)
router-node-selector:: 
Node selector to control placement of router pods
 (string)
router-pod-affinity:: 
Pod affinity label matches to control placement of router pods
 (string)
router-pod-antiaffinity:: 
Pod antiaffinity label matches to control placement of router pods
 (string)
router-ingress-host:: 
Host through which node is accessible when using nodeport as ingress.
 (string)
router-load-balancer-ip:: 
Load balancer ip that will be used for router service, if supported by cloud provider
 (string)
controller-cpu:: 
CPU request for controller pods
 (string)
controller-memory:: 
Memory request for controller pods
 (string)
controller-cpu-limit:: 
CPU limit for controller pods
 (string)
controller-memory-limit:: 
Memory limit for controller pods
 (string)
controller-node-selector:: 
Node selector to control placement of controller pods
 (string)
controller-pod-affinity:: 
Pod affinity label matches to control placement of controller pods
 (string)
controller-pod-antiaffinity:: 
Pod antiaffinity label matches to control placement of controller pods
 (string)
controller-ingress-host:: 
Host through which node is accessible when using nodeport as ingress.
 (string)
controller-load-balancer-ip:: 
Load balancer ip that will be used for controller service, if supported by cloud provider
 (string)
config-sync-cpu:: 
CPU request for config-sync pods
 (string)
config-sync-memory:: 
Memory request for config-sync pods
 (string)
config-sync-cpu-limit:: 
CPU limit for config-sync pods
 (string)
config-sync-memory-limit:: 
Memory limit for config-sync pods
 (string)
timeout:: 
Configurable timeout for the ingress loadbalancer option. (default 2m0s)
 (duration)

* [skupper](skupper.adoc)	 -
