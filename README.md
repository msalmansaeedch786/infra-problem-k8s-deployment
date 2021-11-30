# K8s Solutions

To setup a basic execution environment for the deployment of the following microservices:

* `quotes` which serves a random quote from
* `newsfeed` which aggregates several RSS feeds together
* `front-end` which calls the two previous services and displays the results

## Getting Started

**Containers**, as a way to package and deliver the application code, are here to stay. Building a solution based on containers at scale, that’s where an orchestration platform (e.g. Kubernetes) steps in.
**Kubernetes** provides an easy way to scale the application, compared to virtual machines. It keeps code operational and speeds up the delivery process. Kubernetes API allows automating a lot of resource management and provisioning tasks. Building on top of Kubernetes may also prepare for cloud migration in the future.

## Design Choices and Implementation

**Kubernetes vs AWS ECS**: Kubernetes creates its own private network with its own isolated, secure networking. Vendor agnostic: Unlike Amazon ECS, Kubernetes is a vendor agnostic platform that can run on any cloud provider or on-premises. Kubernetes workloads are portable and support hybrid and multicloud strategies.

**Minikube** is a utility you can use to run Kubernetes (k8s) on your local machine. It creates a single node cluster contained in a virtual machine (VM). This cluster lets you demo Kubernetes operations without requiring the time and resource-consuming installation of full-blown K8s.

## Prerequisite

* Docker with Compose should be installed on the machine
https://docs.docker.com/get-docker/

* Kubectl should be installed on the machine
https://kubernetes.io/docs/tasks/tools/

* Minikube should be installed on the machine
https://minikube.sigs.k8s.io/docs/start/


## Docker Compose Deploymennt

Move to the root directory and run:

```bash
docker-compose up -d

Tear-down:
docker-compose down
```
## Minikube Kubernetes Deploymennt

1. For Quotes:

    Move to the infra-quotes directory and run:

    ```bash
    kubectl apply -f ./k8s
    ```

2. For NewsFeed:

    Move to the infra-newsfeed directory and run:

    ```bash
    kubectl apply -f ./k8s
    ```

3. For Frontend:

    Move to the infra-frontend directory and run:

    ```bash
    kubectl apply -f ./k8s
    ```

## Access Application (front-end)

```bash
kubectl get services

minikube service frontend
```

***Note***: You can also see the k8s workloads using minikube dashboard by running the command: `minikube dashboard`. It will open a web-based UI.