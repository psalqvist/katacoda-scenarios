## Create Kubernetes deployment file

In the kubernetes-tutorial directory, create a file called `deploy.yml` and enter the following content:

```
# configuration for deployment of container to kubernetes

apiVersion: apps/v1
kind: Deployment
metadata:
  name: kubernetes-tutorial-deployment
  labels:
    app: kubernetes-turorial
spec:
  replicas: 1
  selector:
    matchLabels:
      app: kubernetes-tutorial
  template:
    metadata:
      labels:
        app: kubernetes-tutorial
    spec:
      containers:
      - name: nodeserver
        image: <Docker Hub username>/kubernetes-tutorial:latest
        ports:
        - containerPort: 3001
```

The essential things to note here is to match the container image and containerPort with what has been specified in the dockerfile.

Coming up next will be to create the loadbalancer, which will expose our api to the external world.









