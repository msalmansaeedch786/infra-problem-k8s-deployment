# K8S Deployment

To setup a basic execution environment for the deployment of the following microservices:

* `quotes` which serves a random quote from
* `newsfeed` which aggregates several RSS feeds together
* `front-end` which calls the two previous services and displays the results

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