## skupper service unbind

Unbind a target from a service

### Synopsis

Unbind a target from a service

```
skupper service unbind <service-name> <target-type> <target-name> [flags]
```

### Options

```
  -h, --help                      help for unbind
      --target-namespace string   Target namespace for exposed resource
```

### Options inherited from parent commands

```
  -c, --context string      The kubeconfig context to use
      --kubeconfig string   Path to the kubeconfig file to use
  -n, --namespace string    The Kubernetes namespace to use
      --platform string     The platform type to use [kubernetes, podman]
```

### SEE ALSO

* [skupper service](skupper_service.md)	 - Manage skupper service definitions

###### Auto generated by spf13/cobra on 10-Jan-2024
