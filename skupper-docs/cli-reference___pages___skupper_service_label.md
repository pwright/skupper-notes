# skupper service label

Manage service labels

Manage service labels

    skupper service label <service> [labels...]  --[option]

## Examples

    # show labels for my-service
    skupper service label my-service

    # add label1=value1 and label2=value2 to my-service
    skupper service label my-service label1=value1 label2=value2

    # add label1=value1 and remove label2 to/from my-service
    skupper service label my-service label1=value1 label2-

* [skupper service](skupper_service.adoc)	 - Manage skupper service definitions
