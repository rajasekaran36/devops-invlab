---
theme: gaia
_class: lead
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.svg')
marp: true
---

![bg left:40% 80%](https://www.logo.wine/a/logo/Kubernetes/Kubernetes-Logo.wine.svg)

##### ***Innovation Lab***

## CLOUD AND DEVOPS

## ***The Kubernetes***

Dr.S.Rajasekaran 
ASP/IT/KITE

--- 

### How to write slides
Split pages by horizontal ruler (`---`). It's very simple! :satisfied:

**To Start Minikube**
```bash
minikube start
```
**To Start Minikube**
```bash
minikube start
```
---
## Kubernetes
* Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.
* Kubernetes is an orchestrator of containerized cloud-native microservices apps
* Kubernetes deploys and manages applications that are packaged as containers and can easily scale, self-heal, and be updated.
* It was was developed by a group of Google engineers partly in response to Amazon Web Services (AWS) and Docker.
---
### Cloud Native Computing Foundation (CNCF)
* It is a linux foundation project founded in the year 2015 to help advance container technology. 
* In 2014, google open-sourced Kubernetes and donated it to the Cloud Native Computing Foundation (CNCF).
* CNCF Project Category Maturity Levels 
    * SandBox
    * Incubated
    * Graduated
* The levels based on diversity of contribution, community scale/growth, and adoption.
---
### Role of Kubernetes
* Abstractions of Infrastructure
    * It allows allowing businesses to leverage the benefits of on-demand resource provisioning, scalability, and elasticity.
* Simplification of cloud migration
    * Cloud migration is a procedure of transferring applications, data, and other types of business components to any cloud computing platform.
---
### Docker & Kubernetes
* Docker is containerization platform.
* It can roll a container from an image and configure if it's necessary 
* Kubernetes depends on docker for a runtime component called “containerd”.
* Kubernetes also use other runtimes that implemented the Open Container Initiative Standards.
* Docker also has container management concepts like **docker-compose** and **docker-swarm**.
---
### Docker & Kubernetes

![bg center:40% 80%](https://www.arcweb.com/sites/default/files/Images/blog-images-2023/comparison.webp)

---
### Docker & Kubernetes

![bg center:40% 80%](https://www.docker.com/wp-content/uploads/2019/10/Docker-Kubernetes-together.png)

---
### Kubernetes Cluster
* A Kubernetes cluster is one or more nodes providing CPU, memory, and other resources for use by applications.
* There are two types
    * Control Plane Nodes
    * Worker Nodes
* These nodes can run on
    * Physical Servers
    * Virtual Machines
    * Cloud Instances
---
### Control Plane
* The control plane is a collection of system services that implement the brains of Kubernetes. 
* The control plane does
    * Exposes the API
    * Schedules Tasks
    * Implements self-healing
    * Manages scaling operations 
---
### The API server
* The API server is the front end of Kubernetes, and all requests to change and query the state of the cluster go through it.
* Internal control plane services communicate with each other via the API server.
* It exposes a RESTful API over HTTPS.
* All requests are subject to authentication and authorization.
---
### Steps in deployment or updating an application

1. Describe the requirements in a YAML configuration file.
2. Post the configuration file to the API server.
3. The request will be authenticated and authorized.
4. The updates will be persisted in the cluster store.
5. The updates will be scheduled to the cluster.
---

### The Cluster Store
* The cluster store holds the desired state of all applications and cluster components and is the only stateful part of the control plane.
* It is based on etcd distributed database.
etcd is an open source distributed key-value store used to hold and manage the critical information that distributed systems need to keep running.
* It is usually replicated for high availability that to in odd numbers to avoid split brain problem.
---

### Controllers
* Kubernetes uses controllers to implement a lot of the cluster intelligence. They all run on the control plane.
* They are
    * The Deployment controller
    * The StatefulSet controller
    * The ReplicaSet controller
* Kubernetes also runs a controller manager that is responsible for spawning and managing the individual controllers
---
### The scheduler
* Scheduler watches the API server for new work tasks and assigns them to healthy worker nodes.
* It follow the process includes
    * Watching the API server for new tasks
    * Identifying capable nodes
    * Assigning tasks to node
* Identifying nodes by ranking based on nodes **(taints, affinity, anti-affinity rules)**.
* The scheduler marks tasks as pending if it can’t find a suitable node.
---

### Worker Nodes

* It is the node that run the application.
* It contains the components like
* Kublets
    * It is kubernetes agent handles communication between API server.
        * Watches the API server for new tasks
        * Instructs the appropriate runtime to execute tasks
        * Reports the status of tasks to the API server
* Network Proxy
    * Every worker node runs a kube-proxy service that implements cluster networking and load balances traffic to tasks running on the node
* Runtime (containerd runtime and use it to execute tasks)
    * Pulling container images
    * Managing lifecycle operations such as starting and stopping containers.

---
### The Pods

* Pods are the smallest deployable units of computing that you can create and manage in Kubernetes. 
* Kubernetes can run anything includes containers, VMs, Wasmapps and more, so long as you wrap them in Pods.
* Once the pod is ready kubernetes can
    * Choose appropriate nodes
    * Joining networks
    * Attaching volumes
---

### The Pods

![bg center:40% 80%](https://k21academy.com/wp-content/uploads/2020/09/Screenshot-258.png)

---

### Basic Commands

#### **To Start**
* run docker
    * launch the docker desktop app

* run minikube
    * open up command prompt and fire the command

```bash
minikube start
```
---



