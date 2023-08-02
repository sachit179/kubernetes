# kubernetes

kube ctl is comand line tool for kubernetes

minicube

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

