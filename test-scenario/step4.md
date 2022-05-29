## Create the loadbalancer

In the kubernetes-tutorial directory, create a file called `loadBalancer.yml` with the following content:

```
# expose backend using load balancer

apiVersion: v1
kind: Service
metadata:
  name: kubernetes-tutorial-service
spec:
  selector:
    app: kubernetes-tutorial
  type: LoadBalancer
  ports:
  - protocol: TCP
    port: 5000
    targetPort: 3001
    nodePort: 31111
```

- The service created should be of type `LoadBalancer`, protocol to send data should be `TCP`.
- Our service will be exposed on the specified `port` within our Kubernetes cluster.
- `targetPort` is the port on which the service will send requests and
- `nodePort` exposes the service to the external world, and is the port we will use to communicate with our api.

Next up, we will deploy our application to Kubernetes.





