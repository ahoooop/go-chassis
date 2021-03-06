# Kubernetes

Kubernetes discovery is a ServiceDiscovery Plugin,
which leads go-chassis to do service discovery in kubernetes cluster according to Services. 

## Import Path
import in your application code explicitly.
```go
import _ "github.com/go-chassis/go-chassis-extension/registry/kubernetes"
```

## Configurations
If you set servicecomb.registry.type as "kube", 
then "configPath" is necessary to communicate with kubernetes cluster. 
go-chassis will discover k8s Endpoints and Services.

> NOTE: 
> applications with go-chassis must deploy itself as a k8s Pod associate with k8s Service. 
> The Service ports must be named and the port name must be formed as **\<protocol>[-\<suffix>]**. 
> protocol can set to be `rest` or `grpc`. for example: rest, rest-admin, grpc, grpc-legacy

```yaml
servicecomb:
  registry:
    type: kube
    configPath: /etc/.kube/config
```

To see the detailed use case of how to use kube discovery 
with chassis please refer to this 
[example](https://github.com/go-chassis/go-chassis-examples/tree/master/kube).
