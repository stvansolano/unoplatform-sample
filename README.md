# My Codespace

[Twitter: @stvansolano](https://twitter.com/stvansolano)

## Do you like it? Give a Star! :star:

If you like or are using this project to learn or start your own solution, please give it a star. I appreciate it!

A ready-to-use, templated GitHub Codespace that I regularly use for VS Code on GitHub (Codespaces).

## Batteries included

- Docker
- Kubernetes (WIP)
- NodeJS
- .NET 3.1

Extensions

- SQL Server
- Docker
- C#

## Installing Minikube

### Download Minikube

    wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x  minikube-linux-amd64 && sudo mv minikube-linux-amd64 /usr/local/bin/minikube

    minikube config set driver docker

### Start Minikube

    minikube start --force --driver=docker
    minikube version

### Hello K8S!

    kubectl run hello-kube --image=fhsinchy/hello-kube --port=80
    kubectl get pod
    kubectl expose pod hello-kube --type=LoadBalancer --port=80
    minikube service hello-kube

### Minikube commands
    minikube addons enable ingress
    kubectl get pods -n kube-system
    minikube tunnel

## Resources
- https://minikube.sigs.k8s.io/docs/start/
- https://www.freecodecamp.org/news/the-kubernetes-handbook/#installing-kubernetes
- https://www.katacoda.com/courses/kubernetes