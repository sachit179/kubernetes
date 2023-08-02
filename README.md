# kubernetes

https://www.youtube.com/watch?v=s_o8dwzRlu4

## kubernetes architecture 

<img width="715" alt="Screenshot 2023-08-02 at 4 10 37 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/7a689a2d-cd2d-4308-9264-3603a686b3dc">


there is one master noode and many worker node

every worker  node will have kubelet


The Kubelet is responsible for managing the deployment of pods to Kubernetes nodes. It receives commands from the API server and instructs the container runtime to start or stop containers as needed.

kublet also allows nodes in cluster to comunicate with each other

## components of  master node in kubernetees

1. api server : entry point to k8 cluster

2. Controller management : keeps track of whats hapening on cluster

3. scheduler: decides ehich pod to be  scheduled

4. etcd :holds current  state of kubernetees cluster

<img width="710" alt="Screenshot 2023-08-02 at 4 17 02 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/50af3588-7f47-4670-86fb-d5a96e599ad4">

<img width="710" alt="Screenshot 2023-08-02 at 4 17 31 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/6ff2c3f0-6545-4da0-aead-307e7478c3cb">



## note : 

in production there will  be two master node if one fails 


## Main kubernetees components

1. pod smallest unit  in  kubernetees

creates a running environment or layer above container 

<img width="676" alt="Screenshot 2023-08-02 at 4 23 25 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/34151d5c-cfbc-4652-b099-b2e4da763e29">


<img width="773" alt="Screenshot 2023-08-02 at 4 25 17 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/246706ad-0ec6-4e0f-90e5-0f557275a820">

once a container fails a new container will be runed so new ip adress is assigned to that pod so to over come change in ip address service is used

<img width="517" alt="Screenshot 2023-08-02 at 4 27 17 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/a714030e-1403-4307-b08d-c0f2e6ba4d77">


## service and ingress

service is permanent ip address 

even if pod dies service wont die

<img width="773" alt="Screenshot 2023-08-02 at 4 29 22 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/f6d2aedd-4060-47a7-993d-f58d6b0b3879">

ingress is responsible for routing to a particular url

## Configmap and secrets

configmap contains external configuration of our application  eg  database connectiion url

secret  stores password and username


## volume 


## deployment and statefulSet

service also acts as load balancer

defines blueprint for pods

specify how many replicas needed  that bluepriint is called deployment

<img width="718" alt="Screenshot 2023-08-02 at 4 39 08 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/1782b831-9138-4da3-b019-6101955343e7">

we usually  work on deployment  not on pods

statefulset are used for database like mongo sql etc


## kubernetes configuration 

<img width="720" alt="Screenshot 2023-08-02 at 4 47 21 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/f77030cd-c5a4-43d8-b282-1aa0faa3b91e">

<img width="760" alt="Screenshot 2023-08-02 at 4 48 31 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/47566e04-3239-4e49-a6ec-923abb1d2329">


## minikube and kubectl    instalation   <<<<<<<<<<<<< --------------------------------------

## demo project   41 : 20

<img width="602" alt="Screenshot 2023-08-02 at 4 57 18 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/d3f5048e-a04b-4d20-bbb0-825db4659691">


web aplication docker image

<img width="587" alt="Screenshot 2023-08-02 at 4 59 31 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/3b6878ef-e047-4c74-81d0-f980a3c5914b">


## mongo configmap

search kuberntess configmap

<img width="639" alt="Screenshot 2023-08-02 at 5 20 21 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/c9d556e1-08df-4423-ba87-d1adefca39fc">


## mongo secret

<img width="783" alt="Screenshot 2023-08-02 at 5 28 08 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/69d59a75-2788-4fa4-9ac8-cc98b2dc0ba0">

## mongo deployment and service

```
note i have not used mongo config i just took basic enginx eg
```

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80

```

there are metadata and spec section


defining bluprint for pods 

```
template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80
```

Template is configuration of pod that is within configuration of deployment 

template has its  own metadata and specification section


the spec in template is has container

<img width="302" alt="Screenshot 2023-08-02 at 5 39 03 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/ab824ac8-5627-4241-a21e-d8d390d23b34">

<img width="811" alt="Screenshot 2023-08-02 at 5 40 26 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/544bd44b-2ddd-4e34-ace4-7f5f29c610ea">

```
replicas: 3
```

<img width="624" alt="Screenshot 2023-08-02 at 5 42 46 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/ecd75283-a5c2-440f-ac32-5387edf0365c">


### service section

<img width="700" alt="Screenshot 2023-08-02 at 5 45 08 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/a4e35c67-c274-4d5a-aeba-87474a144d05">

<img width="1353" alt="Screenshot 2023-08-02 at 5 47 41 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/d5295e10-8725-4a0a-b062-7d91f9021127">


## web app deployment and service


## environment variable

<img width="1312" alt="Screenshot 2023-08-02 at 5 52 58 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/615e610d-f4b1-43c4-89a1-5138bf29300d">


## pass config data to webapp deployment 

when web  app starts it needs to connect to mongo db 

<img width="678" alt="Screenshot 2023-08-02 at 6 13 26 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/71d12ac8-8524-4f56-8919-e0b4bdcb23d5">


## configure external service

<img width="777" alt="Screenshot 2023-08-02 at 6 15 33 PM" src="https://github.com/sachit179/kubernetes/assets/140412932/757211ce-a8b0-4795-94e2-1b911d9075c3">


## deploy all resources to minikube cluters

```
minikube start
```

```
kubectl get pod
```

```
kubectl apply -f mongo-config.yaml
```

```
kubectl apply -f mongo-secret.yaml
```


```
kubectl apply -f mongo.yaml
```

```
kubectl apply -f webapp.yaml
```

## interacting with clustters

```
kubectl get all
```

```
kubectl get configmap
```

```
kubectl get secret
```

```
kubectl get pod
```

```
kubectl --help
```


## acess webapp on drowser

```
kubectl get svs
```

```
minikube ip
```
 or 
```
kubectl get  node -o wide
```
