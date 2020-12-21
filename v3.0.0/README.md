# Deploying Version 3.0.0

Start your minikube cluster with:

```bash
minikube start --vm
```

Enable the Ingress add-on with:

```bash
minikube addons enable ingress
```

Instead of uploading the Docker image to a registry, you can create the image in the cluster directly.

Connect to the Docker daemon inside minikube with:

```bash
minikube docker-env
# follow the instructions in the output
```

You Docker CLI is connected to the Docker daemon inside minikube.

You can create the Docker image with:

```bash
docker build -t labv3 .
```

Create a namespace with:

```bash
kubectl create namespace labv3
```

Deploy all of the resources with:

```bash
kubectl apply -f deployment.yaml --namespace labv3
```

Retrieve the IP address of minikube with:

```bash
minikube ip
```

Check that the application was deployed correctly with:

```bash
curl --header 'Host: k8s-is-great.com' http://<replace with minikube ip>
```
