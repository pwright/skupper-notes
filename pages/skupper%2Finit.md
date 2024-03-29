title:: skupper/init

- You must initialise skupper in a namespace before you can access a service network.
- You can initialise skupper using one of the following methods:
	- CLI `skupper init`
	- Operator `skupper-site ConfigMap`
	- YAML, create SA, roles and  `skupper-site-controller` deployment
-
- Using cli - [[skupper_init]]
- Using yaml
	- core options
		- SiteConfigNameKey                string = [[name]]
		- SiteConfigRouterModeKey          string = [[router-mode]]
		- SiteConfigIngressKey             string = [[Ingress]]
		- SiteConfigIngressAnnotationsKey  string = [[site.ingress-annotations]]
		- SiteConfigIngressHostKey         string = [[ingress-host]]
		- SiteConfigCreateNetworkPolicyKey string = [[create-network-policy]]
		- SiteConfigRoutersKey             string = [[routers]]
	- console options
		- SiteConfigConsoleKey               string = [[console]]
		- SiteConfigConsoleAuthenticationKey string = [[console-authentication]]
		- SiteConfigConsoleUserKey           string = [[console-user]]
		- SiteConfigConsolePasswordKey       string = [[console-password]]
		- SiteConfigConsoleIngressKey        string = [[console-ingress]]
	- router options
	  collapsed:: true
		- SiteConfigRouterConsoleKey            string = [[router-console]]
		- SiteConfigRouterLoggingKey            string = [[router-logging]]
		- SiteConfigRouterDebugModeKey          string = [[router-debug-mode]]
		- SiteConfigRouterCpuKey                string = [[router-cpu]]
		- SiteConfigRouterMemoryKey             string = [[router-memory]]
		- SiteConfigRouterCpuLimitKey           string = [[router-cpu-limit]]
		- SiteConfigRouterMemoryLimitKey        string = [[router-memory-limit]]
		- SiteConfigRouterAffinityKey           string = [[router-pod-affinity]]
		- SiteConfigRouterAntiAffinityKey       string = [[router-pod-antiaffinity]]
		- SiteConfigRouterNodeSelectorKey       string = [[router-node-selector]]
		- SiteConfigRouterMaxFrameSizeKey       string = [[xp-router-max-frame-size]]
		- SiteConfigRouterMaxSessionFramesKey   string = [[xp-router-max-session-frames]]
		- SiteConfigRouterIngressHostKey        string = [[router-ingress-host]]
		- SiteConfigRouterServiceAnnotationsKey string = [[router-service-annotations]]
		- SiteConfigRouterLoadBalancerIp        string = [[router-load-balancer-ip]]
	- controller options
		- SiteConfigServiceControllerKey            string = [[service-controller]]
		- SiteConfigServiceSyncKey                  string = [[service-sync]]
		- SiteConfigControllerCpuKey                string = [[controller-cpu]]
		- SiteConfigControllerMemoryKey             string = [[controller-memory]]
		- SiteConfigControllerCpuLimitKey           string = [[controller-cpu-limit]]
		- SiteConfigControllerMemoryLimitKey        string = [[controller-memory-limit]]
		- SiteConfigControllerAffinityKey           string = [[controller-pod-affinity]]
		- SiteConfigControllerAntiAffinityKey       string = [[controller-pod-antiaffinity]]
		- SiteConfigControllerNodeSelectorKey       string = [[controller-node-selector]]
		- SiteConfigControllerIngressHostKey        string = [[controller-ingress-host]]
		- SiteConfigControllerServiceAnnotationsKey string = [[controller-service-annotations]]
		- SiteConfigControllerLoadBalancerIp        string = [[controller-load-balancer-ip]]
	- config-sync options
		- SiteConfigConfigSyncCpuKey         string = [[config-sync-cpu]]
		- SiteConfigConfigSyncMemoryKey      string = [[config-sync-memory]]
		- SiteConfigConfigSyncCpuLimitKey    string = [[config-sync-cpu-limit]]
		- SiteConfigConfigSyncMemoryLimitKey string = [[config-sync-memory-limit]]