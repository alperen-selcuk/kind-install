## kind-install

this shell script install KinD requirements (docker, kubectl) and create 1 master 3 worker node.


### ekstra port mapping

if you want use ingress or NodePort you need to expose docker port to kind node.

```
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
name: cluster
nodes:
- role: control-plane
  extraPortMappings:
  - containerPort: 31000
    hostPort: 80
    listenAddress: "0.0.0.0"
    protocol: TCP
```
