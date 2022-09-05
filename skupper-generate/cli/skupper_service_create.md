## skupper service create

Create a skupper service

```
skupper service create <name> <port...> [flags]
```

### Options

```
      --aggregate string   The aggregation strategy to use. One of 'json' or 'multipart'. If specified requests to this service will be sent to all registered implementations and the responses aggregated.
      --enable-tls         If specified, the service communication will be encrypted using TLS
      --event-channel      If specified, this service will be a channel for multicast events.
  -h, --help               help for create
      --mapping string     The mapping in use for this service address (currently one of tcp or http) (default "tcp")
```

### Options inherited from parent commands

```
  -c, --context string      The kubeconfig context to use
      --kubeconfig string   Path to the kubeconfig file to use
  -n, --namespace string    The Kubernetes namespace to use
```

### SEE ALSO

* [skupper service](skupper_service.md)	 - Manage skupper service definitions

###### Auto generated by spf13/cobra on 11-May-2022