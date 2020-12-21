# Packaging and deploying in Kubernetes

You can create the Docker image for the following application with:

```bash
docker build -t <your_docker_hub_username>/first-k8s-app:1.0.0 .
```

You can push the image to the Docker Hub registry with:

```bash
docker push <your_docker_hub_username>/first-k8s-app:1.0.0
```

Start your minikube cluster with:

```bash
minikube start --vm
```

Enable the Ingress add-on with:

```bash
minikube addons enable ingress
```

Deploy all of the resources with:

```bash
kubectl apply -f kube
```

Retrieve the IP address of minikube with:

```bash
minikube ip
```

Visit the application at `http://<minikube-ip>/second`
