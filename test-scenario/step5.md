## Deploy application to Kubernetes

Now, it is time for deployment.

Our katacoda environment should have minicube and kubectl integrated. Run minikube by entering `minikube start` from the terminal. Check the status by running `minikube status`. This should give us the following output:

```
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured
timeToStop: Nonexistent
```

Let´s first run the deployment by running `kubectl apply -f deploy.yml`. Move on to run `kubectl get deployment`, this should generate the following output:

```
NAME                         READY   UP-TO-DATE   AVAILABLE   AGE
kubernetes-test-deployment   1/1     1            1           34h
```

It could take a few minutes for `READY` to go from `0/1` to `1/1`. When it does, run the following to run the loadbalancer:

```
kubectl apply -f loadBalancer.yml
```

Now we can run `kubectl get svc` to get information regarding our service. This should render something similar to the following:

```
kubernetes-tutorial-service   LoadBalancer   10.103.164.36   <pending>     5000:31111/TCP   34h
```

Run `minikube service kubernetes-tutorial-service`. The output should now give you a column named `URL`. This shouuld mean that we can reach our endpoints using this URL.

Try this by running `curl <url>` from the terminal, which should give us the following: `{success: true}`

This means we have deployed our application to Kubernetes succesfully, congratulations!


