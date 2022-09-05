## skupper unexpose

Unexpose a set of pods previously exposed through a Skupper address

```
skupper unexpose [deployment <name>|pods <selector>|statefulset <statefulsetname>|service <name>] [flags]
```
### Options

```
    --address string   Skupper address the target was exposed as
-h, --help             help for unexpose
```
### Options inherited from parent commands

```
-c, --context string      The kubeconfig context to use
    --kubeconfig string   Path to the kubeconfig file to use
-n, --namespace string    The Kubernetes namespace to use
```
### SEE ALSO

* [skupper](skupper.md)	 -
###### Auto generated by spf13/cobra on 11-May-2022
-