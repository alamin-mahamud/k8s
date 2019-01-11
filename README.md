# Kubernetes Primer
automatic deployment, scaling and management of containerized applications.

groups containers that make up an application into logical units for easy management and discovery.

## Kubernetes Basic Features
1. Service Discovery
   - kubernetes gives containers their own IP addresses and a single DNS name for a set of containers and can load-balance across them
2. Automatic Binpacking
   - automatically places containers based on their resource requirements and other containers, while not sacrificing availability.
3. Storage Orchestration
   - local storage / cloud (GCP/AWS) / network storage such as NFS, iSCSI, Gluster, Ceph, Cinder, Flocker
4. Self-healing
   - restarts containers that fail
   - replaces and reschedules containers when nodes die,
   - kills containers that dont respond to your user-defined health check, and doesn't advertise them until they are ready to serve.
5. Automated rollouts and rollbacks
   - progressively rolls out changes to your application, or configuration, while monitoring application health.
   - all instances are not kill at same time.
   - if something goes wrong, kubernetes will rollback the change for you.
6. secret and configuration management 
   - deploy and update secrets and application configuration
   - w/o rebuilding your image and w/o exposing secrets in your stack configuration
7. batch execution - batch and CI workloads, replacing containers that fail, if desired.
8. horizontal scaling

## Setup
### Local Machine Solutions
* Minikube 
  - single node kubernetes cluster
* Minishift 
  - community version of kubernetes enterprise platform
  - Openshift for local development & testing.
* microk8s
  - single command installation of latest kubernetes release.
* IBM Cloud Private-CE or IBM Cloud Private-CE on Linux Containers
* kubadm-dind
  - multinode (while minikube is single-node) kubernetes cluster. only requires a docker daemon. docker-in-docker to spawn the kubernetes cluster.
* Ubuntu on LXD supports a nine-instance deployment on localhost.

## Creating a custom cluster from scratch
### Designing and Preparing
* Cloud Provider
  * provides an interface for managing TCP Load Balancers, Nodes(instances) and Networking Routes
  * **TCP Load Balancer** - verifies information sent to IP addresses. ensures the data arrives error-free to non-HTTP applications.
* Nodes
  * **x86_64 architecture** - 
* Network
  * container to container - solved by pods
  * pod to pod
  * pod to service - services
  * external to service - services
  
