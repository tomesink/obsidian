# Cloud native training (containers)

## Cloud native training (containers)

Monotlithic apps -> VM (which are huge waste of resources for a small several MB services -> containers

Service - its like unix utility - small doing one and one thing only and doing it good/perfect

**Container**: self-contained unit od software. It contains everything required to run the code.  Container includes code, configs, processes, networking, dependencies bundled up and just enough Operating System 9linux) or tiny OS tu run the code. Each container has its own little linux world.

In almost all cases, the host OS kernel is shared. To run a different kernel you need to use virtualization. This is rare and only used when necessary due to performance degradation.
"The Docker Engine container comprises just the application and its dependencies. 

**It runs as an isolated process in userspace on the host operating system, sharing the kernel with other containers. **
**
**
**There is no kernel in a Docker image**. This is the fundamental and most important difference between a virtual machine and a Docker container.

The images named as operating systems distributions such as ubuntu, debian, ... **are not operating systems**, but are rather** images with filesystem structure and tools that you typicaly find in an ubuntu** distribution for example.

So in short, the **docker container always uses the kernel of the host machine where it is running.**

Docker is a program that manages all the containers - sets them up, monitors them, and tear down.

Red hat Linux container with database can be acessed by ubuntu linux web server. Web server can acces to suse redis database. Containers can communicate:

![Cloud native training (containers)](images/Cloud%20native%20training%20(containers).png)

**Image**: Its a file with enough operating system tu run what you need. Enough OS - not a kernel or distro, just File System and libraries and distro specific tools. COntainer runs as a separate proces not aseparate OS.

**Image -> docker run -> Running Container **on which you can install any programs and dependencies you want.

**stopped customized container -> docker commit -> new image**

NOTE: original base image is untouched.

docker commit —container-custom-name —my-image-name

Docker instance: A runtime instance of a Docker image conaining:
	1. A docker image
	2. An execution environment
	3. A standard set of instructions

**VM vs container**:

**VM** - The **entire guest operating system**. one or many applications. The necessary binaries and libraries. 
**x**
**container** - its a **process, not OS**. contains linux filesystem and tools but the kernel is shared with host OS kernel. It does not include the linux kernel or OS. Just tiny part of it. includes one application and all of its dependencies. Not tied to infrastructure. it only needs a docker engine installed to host. 

Devops benefits: consistent environments - no process difference betveen dev and production environments
	simple scaling - fast deployment. 
**Devops team can isolate and debug issues at the container level.**

## Kubernetes

Container orchestrator. Manages all the containers, deploys multiple containers.
	1. provision hosts (nodes)
	2. Instantiate containers on a host (inside a POD)
	3. Restart failing containers
	4. expose containers as services outside the cluster
	5. Scale the cluster up or down.

K8s is a platform to schedule and run containers on clusters of virtual machines. It runs on bare metal, virtual machines, private datacenter and public clouds.

Plug and play architecture. extend architecture when needed. Lots of add-ons ( network drivers, service discovery, container runtime, visualisation, commands), persistent storage, logging and monitoring etc.

**### Architecture**

![Cloud native training (containers)-1](images/Cloud%20native%20training%20(containers)-1.png)

**master node **- responsible for overall management of k8s cluster

**API server** - responsible for communication. Interacts with k8s api. Its a kubernetes frontend

**Scheduler** -  process which assigns Pods to Nodes. The scheduler determines which Nodes are valid placements for each Pod in the scheduling queue according to constraints and available resources.

**Controller Manager **- runs controllers. A **controller** is a background thread that runs tasks on aa cluster **
**
**
**
**kubectl** - command line app to interact with kubernetes. Informs master node about the node and POD/container states.

**kubeconfig** - config file with acces/authentication information, server information for acessing the API server.

**etcd** - its a K8s plugin. its basically a key-value store and stores all cluster data.

**(Work) Node **- node where the application operates

**kubelet** - a process for communicating between worker node and API server on master node 

**kube-proxy** - process for network proxy and LB for a service on a single worker node. It handles network routing

**docker** - runs containers on the node

**POD** - a smallest unit which can be deployed ok k8s node. It must contain at least one container. PODs share resources of a node. Can be exposed to the Internet via kube-proxy or communicate with other nodes via kube-proxy. **This is how end user talks to kubernetes.**

## Cloud Native: 

**Building and deploying CN apps:**

	gRPC  **Google Remote Procedure Call**. Like SOAP or REST, its a request-response based system. 

RPC -s a form of client–server interaction (caller is client, executor is server), typically implemented via a request–response message-passing system.

payload between client and server is called **ProtocolBufer** (binary serialization structures of data). gRPC is robust, fast (runs on HTTP2). gRPC easily crate clients. The clients do not need to maintain libraries. clients by defaults can create their own libraries to talk to the server.
	gRPC has layered design which enable extenstion.

	**No need to think weather a request should be PUT or POST.**

**Coordination & Service Discovery:** Consul, CoreDNS, etcd

**	ETCD** its basically a key-value store and stores all cluster data. Kubernetes uses etcd to store all its data – its configuration data, its state, and its metadata.
	**CoreDNS** - replaces kube-DNS as DNS tool for K8s. Its a K8s plugin. 
	**Consul** - service discovery & configuration functionality. 

**Service discovery** is the actual process of figuring out how to connect to a service.

Discovery Service provides the functionality and interface for external clients to discover data access endpoints. Discovery Service is an action of finding a service provider for a requested service. The Discovery service retrieves the address of the service provider. This location of the demanded service is further accessed and used. 

	• Client: Entity that is interested in finding and using a service
	• Server: Entity that offers discovery service to clients
	• Endpoint: A node in the Virtual Network Function(VNF) or service/POD in Cloud Native Function that provides the service required by the clients

**Managing Services/ load balancing**: 
	**Linkerd** - latency-aware load balancing, connection pooling, TLS. results in more scalable and resilient apps.
	**Envoy** - similar to linkerd. supports advanced load balancing. unlike linkerd its highly configurable, provides API for configuration management
	

**Networking:** Early issues with container networking: no standards for networking vendors to integrate their network stack with kubernetes. Developers did not know which network provider to choose. Switching providers led to integration issues. 
The solution:
	**Container Network Interface** - generic plugin based networking solution for containers. virtual interfaces,  network config is in JSON. Calico, DANM - Nokia **CNI. **The networking vendors should adhere to CNI specs.

	1. Container runtime creates new network namespace for the container before any plugin.
	2. Runtime determines which networks the container should belong to and which plugins to execute.
    	3. Runtime adds the container to each network, executing the corresponding plugins for each network sequentially

**Storage**: 
	**Ceph** - distributed storage system for file, block and object storage
	**GlusterFS** - distributed file system, supports automatic failover, no centralized metadata server. Centos 7/8 has a variety of packages for GlusterFS
 
**LCM**: **Rook** brings file, block and object storage systems into the Kubernetes ecosystem. Orchestrates Ceph on top of Kubernetes

**Runtime**: **Containerd** - industry standard container runtime. it manages the complete container lifecycle of the host system:
	- Image transfer and storage
	- Container execution and supervision
	- Low-level storage and network attachments

**Application Monitoring:** **Prometheus**(performance metrics) PromQL for rules and monitoring, **Grafana** - front end for visualisation Prometheus metrics,

**Logging**: **fluentd** , Beats/**Elk** (elastic stack). Log aggregation. fluentd more performant

**Tracing**: used for debugging CNF. **Jaeger**, OpenTracing, Zipkin. Its about intstrument our application with the required Jaeger start and finish functions in our API. How long the call should take.

**Security**: Issue - passing contextual data to a container - usernames, passwords, keys. These might be sent to a container as environment variables and end up to be stored. 
	HashiCorp **Vault** to store sensitive data in a secure manner and encrypted.
	**TUF** - a framework or specification for security hardening of SW updates vurnerable to attacks. This framework adresses problem by providing developers tools that can be integrated with any SW update system.
	**Notary** - most mature implementation of **TUF** 
	**Clair** - for scanning images and finding vulnerabilities
	**Aquasec**: for complete security platform

## Devops

My role: seamless provisioning infrastracture and deploying either Cloud Native Products and applications (kubernetes) or Virtual Network Functions on OpenStack.

### Terraform

Automation and managing infrastructure, platform and services running on the platform.

Tool for **infrastructure** **provisioning**, eg. several servers with microservices, networking, dockers, kubernetes etc, security etc. The deployment is done afterwards.

Uses declarative config language: define WHAT to do and teraform will figure out how to do that.

**Provisioning**:  create virtual servers, create AWS users and permissions, spin up servers, install docker, set up (virtual) networking, storage, databases … everything in correct order.

**Deployment**: After infrastructure is provisioned, we can deploy particualr apps, services.

**Ansible** - infrastructure as code. Mainly configuration tool comes to play after terraform (once the inrastructure is provisioned). Configure infrastructure, deploy apps, install/update software. More mature tool. With one config you can configure multiple remote servers.

vs

**Terraform** - infrastructure as code and provisioning. CAN deploy apps. Relativelu new. More advanced in orchestration.

They somehow overlaps but can do different things. Terraform better for provisioning infrastructure and Ansible better for configuring that infrastructure and make changes in it.

### Openstack:  ### Nova - compute, Glance - Images, Networking - neutron (legacy now). anti affinity rules configuration.### 

pozice:

IBM: linuxovy administrator, patchovani, skripty

Tieto: product architekt - analytik, prevod requirementu do designu, UML, sekvencni diagramy, diagramy trid, hodne o sitich. C++. design a analyza novych featur nad telco databazi subscriberu. ERD modelovani - nikoliv vytvareni novych databazi ale spise jejich modifikace a rozsirovani pridavani novych entit. Navrh pak posilan do indie nebo budapesti programatorum

iOS: vyvoj aplikaci from scratch, testy, automatizace od commitu do app store.

Nokia: SW architect - v podstate to podobne jako prace v Tietu, navrh novych featur na jedne komponente

System engineer: devops, vyvoj CICD reseni pro nokia databazove produkty, psani automatizacnich skriptu v pythonu - stahnout balicek, rozbalit, nainstalovat, deploynout Nokia container system na Openstack - to z velke casti kubernetes plus proprietarni nastroje jako naprs. backup, monitoring.

Solution Architect: uz ne design jednotlivych featur, ale komplexnich reseni jednotlivych komponentu, UML, BPMN, uz ne class diagramy ale spise high level tedy objektove/konceptualni diagramy

Obecne hodne o sitich resp. komunikaci mezi jednotlivymi komponentami nebo microservices, posilani zprav, rozhodovaci diagramy funkcionalit - co ma delat za jake situace. hodne o linuxu, Openstacku, cloudu

