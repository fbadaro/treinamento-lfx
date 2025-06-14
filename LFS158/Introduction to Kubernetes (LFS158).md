# 01. Introduction to Kubernetes (LFS158)

Is your team beginning to use Kubernetes for container orchestration? Do you need guidelines on how to start transforming your organization with Kubernetes and cloud-native patterns? Would you like to simplify software container orchestration and find a way to grow your use of Kubernetes without adding infrastructure complexity? Then this is the course for you!

In this course, we will discuss some of Kubernetes' basic concepts and talk about the architecture of the system, the problems it solves, and the model that it uses to handle containerized deployments and scaling.

This course offers an introduction to Kubernetes and includes technical instructions on how to deploy a stand-alone and multi-tier application. You will learn about ConfigMaps and Secrets, and how to use Ingress.

Upon completion, developers will have a solid understanding of the origin, architecture and building blocks for Kubernetes, and will be able to begin testing the new cloud-native pattern to begin the cloud-native journey.

By the end of this course, you should be able to:

- Discuss the origin, architecture, primary components and building blocks of Kubernetes.
- Set up and access a Kubernetes cluster using Minikube.
- Run applications on the deployed Kubernetes environment, and access the deployed applications.
- Discuss the usefulness of Kubernetes communities, and how you can participate.

# 02. From Monolith to Microservices

Most new companies today run their business processes in the cloud. Newer startups and enterprises which realized early enough the direction technology was headed developed their applications for the cloud.
>
Not all companies were so fortunate. Some built their success decades ago on top of legacy technologies - monolithic applications with all components tightly coupled and almost impossible to separate, a nightmare to manage and deployed on super expensive hardware.

If working for an organization which refers to their main business application "the black box", where nobody knows what happens inside and most logic was never documented, leaving everyone clueless as to what and how things happen from the moment a request enters the application until a response comes out, and you are tasked to convert this business application into a cloud-ready set of applications, then you may be in for a very long and bumpy ride.

## The Legacy Monolith

Although most enterprises believe that the cloud will be the new home for legacy applications, not all legacy applications are a fit for the cloud, at least not yet.

Moving an application to the cloud should be as easy as walking on the beach and collecting pebbles in a bucket and easily carrying them wherever needed. A 1000-ton boulder, on the other hand, is not easy to carry at all. This boulder represents the monolith application - sedimented layers of features and redundant logic translated into thousands of lines of code, written in a single, not so modern programming language, based on outdated software architecture patterns and principles.

In time, the new features and improvements added to code complexity, making development more challenging - loading, compiling, and building times increase with every new update. However, there is some ease in administration as the application is running on a single server, ideally a Virtual Machine or a Mainframe.

A monolith has a rather expensive taste in hardware. Being a large, single piece of software which continuously grows, it has to run on a single system which has to satisfy its compute, memory, storage, and networking requirements. The hardware of such capacity is not only complex and extremely pricey, but at times challenging to procure.

Since the entire monolith application runs as a single process, the scaling of individual features of the monolith is almost impossible. It internally supports a hardcoded number of connections and operations. However, scaling the entire application can be achieved by manually deploying a new instance of the monolith on another server, typically behind a load balancing appliance - another pricey solution.

During upgrades, patches or migrations of the monolith application downtime is inevitable and maintenance windows have to be planned well in advance as disruptions in service are expected to impact clients. While there are third party solutions to minimize downtime to customers by setting up monolith applications in a highly available active/passive configuration, they introduce new challenges for system engineers to keep all systems at the same patch level and may introduce new possible licensing costs.

## The Modern Microservice

Pebbles, as opposed to the 1000-ton boulder, are much easier to handle. They are carved out of the monolith, separated from one another, becoming distributed components each described by a set of specific characteristics. Once weighed all together, the pebbles make up the weight of the entire boulder. These pebbles represent loosely coupled microservices, each performing a specific business function. All the functions grouped together form the overall functionality of the original monolithic application. Pebbles are easy to select and group together based on color, size, shape, and require minimal effort to relocate when needed. Try relocating the 1000-ton boulder, effortlessly.

Microservices can be deployed individually on separate servers provisioned with fewer resources - only what is required by each service and the host system itself, helping to lower compute resource expenses.

Microservices-based architecture is aligned with Event-driven Architecture and Service-Oriented Architecture (SOA) principles, where complex applications are composed of small independent processes which communicate with each other through Application Programming Interfaces (APIs) over a network. APIs allow access by other internal services of the same application or external, third-party services and applications.

Each microservice is developed and written in a modern programming language, selected to be the best suitable for the type of service and its business function. This offers a great deal of flexibility when matching microservices with specific hardware when required, allowing deployments on inexpensive commodity hardware.

Although the distributed nature of microservices adds complexity to the architecture, one of the greatest benefits of microservices is scalability. With the overall application becoming modular, each microservice can be scaled individually, either manually or automated through demand-based autoscaling.

Seamless upgrades and patching processes are other benefits of microservices architecture. There is virtually no downtime and no service disruption to clients because upgrades are rolled out seamlessly - one service at a time, rather than having to recompile, rebuild and restart an entire monolithic application. As a result, businesses are able to develop and roll-out new features and updates a lot faster, in an agile approach, having separate teams focusing on separate features, thus being more productive and cost-effective

## Refactoring

Newer, more modern enterprises possess the knowledge and technology to build cloud-native applications that power their business.

Unfortunately, that is not the case for established enterprises running on legacy monolithic applications. Some have tried to run monoliths as microservices, and as one would expect, it did not work very well. The lessons learned were that a monolithic size multi-process application cannot run as a microservice and that other options had to be explored. The next natural step in the path of the monolith to microservices transition was refactoring. However, migrating a decades-old application to the cloud through refactoring poses serious challenges and the enterprise faces the refactoring approach dilemma: a "Big-bang" approach or an incremental refactoring.

A so-called "Big-bang" approach focuses all efforts with the refactoring of the monolith, postponing the development and implementation of any new features - essentially delaying progress and possibly, in the process, even breaking the core of the business, the monolith.

An incremental refactoring approach guarantees that new features are developed and implemented as modern microservices which are able to communicate with the monolith through APIs, without appending to the monolith's code. In the meantime, features are refactored out of the monolith which slowly fades away while all, or most its functionality is modernized into microservices. This incremental approach offers a gradual transition from a legacy monolith to modern microservices architecture and allows for phased migration of application features into the cloud.

Once an enterprise chooses the refactoring path, there are other considerations in the process. Which business components to separate from the monolith to become distributed microservices, how to decouple the databases from the application to separate data complexity from application logic, and how to test the new microservices and their dependencies, are just a few of the decisions an enterprise is faced with during refactoring.

The refactoring phase slowly transforms the monolith into a cloud-native application which takes full advantage of cloud features, by coding in new programming languages and applying modern architectural patterns. Through refactoring, a legacy monolith application receives a second chance at life - to live on as a modular system adapted to fully integrate with today's fast-paced cloud automation tools and services.

## Challenges

The refactoring path from a monolith to microservices is not smooth and without challenges. Not all monoliths are perfect candidates for refactoring, while some may not even "survive" such a modernization phase. When deciding whether a monolith is a possible candidate for refactoring, there are many possible issues to consider.

When considering a legacy Mainframe based system, written in older programming languages - Cobol or Assembler, it may be more economical to just re-build it from the ground up as a cloud-native application. A poorly designed legacy application should be re-designed and re-built from scratch following modern architectural patterns for microservices and even containers. Applications tightly coupled with data stores are also poor candidates for refactoring.

Once the monolith survived the refactoring phase, the next challenge is to design mechanisms or find suitable tools to keep alive all the decoupled modules to ensure application resiliency as a whole.

Choosing runtimes may be another challenge. If deploying many modules on a single physical or virtual server, chances are that different libraries and runtime environments may conflict with one another, causing errors and failures. This forces deployments of single modules per servers in order to separate their dependencies - not an economical way of resource management, and no real segregation of libraries and runtimes, as each server also has an underlying Operating System running with its libraries, thus consuming server resources - at times the OS consuming more resources than the application module itself.

Eventually a solution emerged to tackle these refactoring challenges. Application containers came along providing encapsulated lightweight runtime environments for application modules. Containers promised consistent software environments for developers, testers, all the way from Development to Production. Wide support of containers ensured application portability from physical bare-metal to Virtual Machines, but this time with multiple applications deployed on the very same server, each running in their own execution environments isolated from one another, thus avoiding conflicts, errors, and failures. Other features of containerized application environments are higher server utilization, individual module scalability, flexibility, interoperability and easy integration with automation tools.

# 03. Container Orchestration

Container images allow us to confine the application code, its runtime, and all of its dependencies in a pre-defined format. The container runtimes like runC, containerd, or cri-o can use pre-packaged images as a source to create and run one or more containers. These runtimes are capable of running containers on a single host, however, in practice, we would like to have a fault-tolerant and scalable solution, achieved by building a single controller/management unit, a collection of multiple hosts connected together. This controller/management unit is generally referred to as a container orchestrator.

In this chapter, we will explore why we should use container orchestrators, different implementations of container orchestrators, and where to deploy them.

By the end of this chapter, you should be able to:

- Define the concept of container orchestration.
- Explain the benefits of using container orchestration.
- Discuss different container orchestration options.
- Discuss different container orchestration deployment options.

## What Are Containers?

Before we dive into container orchestration, let's review first what containers are.

Containers are an application-centric method to deliver high-performing, scalable applications on any infrastructure of your choice. Containers are best suited to deliver microservices by providing portable, isolated virtual environments for applications to run without interference from other running applications.

![alt text](01.png "Containers")

### Container Deployment

Microservices are lightweight applications written in various modern programming languages, with specific dependencies, libraries and environmental requirements. To ensure that an application has everything it needs to run successfully it is packaged together with its dependencies.

Containers encapsulate microservices and their dependencies but do not run them directly. Containers run container images.

A container image bundles the application along with its runtime, libraries, and dependencies, and it represents the source of a container deployed to offer an isolated executable environment for the application. Containers can be deployed from a specific image on many platforms, such as workstations, Virtual Machines, public cloud, etc.


## What Is Container Orchestration?

In Development (Dev) environments, running containers on a single host for development and testing of applications may be a suitable option. However, when migrating to Quality Assurance (QA) and Production (Prod) environments, that is no longer a viable option because the applications and services need to meet specific requirements:

- Fault-tolerance
- On-demand scalability
- Optimal resource usage
- Auto-discovery to automatically discover and communicate with each other
- Accessibility from the outside world
- Seamless updates/rollbacks without any downtime.

Container orchestrators are tools which group systems together to form clusters where containers' deployment and management is automated at scale while meeting the requirements mentioned above. The clustered systems confer the advantages of distributed systems, such as increased performance, cost efficiency, reliability, workload distribution, and reduced latency.

## Container Orchestrators

With enterprises containerizing their applications and moving them to the cloud, there is a growing demand for container orchestration solutions. While there are many solutions available, some are mere re-distributions of well-established container orchestration tools, enriched with features and, sometimes, with certain limitations in flexibility.

Although not exhaustive, the list below provides a few different container orchestration tools and services available today:

- Amazon Elastic Container Service
- Azure Container Instances
- Azure Service Fabric
- Kubernetes
- Nomad
- Docker Swarm

Container orchestrators are also explored in another Linux Foundation course, "Introduction to Cloud Infrastructure Technologies" (LFS151). We highly recommend that you take this course.

## Why Use Container Orchestrators?

Although we can manually maintain a couple of containers or write scripts to manage the lifecycle of dozens of containers, orchestrators make things much easier for users especially when it comes to managing hundreds or thousands of containers running on a global infrastructure.

Most container orchestrators can:

- Group hosts together while creating a cluster, in order to leverage the benefits of distributed systems.
- Schedule containers to run on hosts in the cluster based on resources availability.
- Enable containers in a cluster to communicate with each other regardless of the host they are deployed to in the cluster.
- Bind containers and storage resources.
- Group sets of similar containers and bind them to load-balancing constructs to simplify access to containerized applications by creating an interface, a level of abstraction between the containers and the client.
- Manage and optimize resource usage.
- Allow for implementation of policies to secure access to applications running inside containers.

With all these configurable yet flexible features, container orchestrators are an obvious choice when it comes to managing containerized applications at scale. In this course, we will explore Kubernetes, one of the most in-demand container orchestration tools available today.

## Where to Deploy Container Orchestrators?

Most container orchestrators can be deployed on the infrastructure of our choice - on bare metal, Virtual Machines, on-premises, on public and hybrid clouds. Kubernetes, for example, can be deployed on a workstation, with or without an isolation layer such as a local hypervisor or container runtime, inside a company's data center, in the cloud on AWS Elastic Compute Cloud (EC2) instances, Google Compute Engine (GCE) VMs, DigitalOcean Droplets, IBM Virtual Servers, OpenStack, etc.

In addition, there are turnkey cloud solutions which allow production Kubernetes clusters to be installed, with only a few commands, on top of cloud Infrastructures-as-a-Service. These solutions paved the way for the managed container orchestration as-a-Service, more specifically the managed Kubernetes as-a-Service (KaaS) solution, offered and hosted by the major cloud providers. Examples of KaaS solutions are Amazon Elastic Kubernetes Service (Amazon EKS), Azure Kubernetes Service (AKS), DigitalOcean Kubernetes, Google Kubernetes Engine (GKE), IBM Cloud Kubernetes Service, Oracle Container Engine for Kubernetes, or VMware Tanzu Kubernetes Grid.

# 04. Kubernetes

In this chapter, we describe Kubernetes, its features, and the reasons why you should use it. We will explore the evolution of Kubernetes from Borg, Google's very own distributed workload manager.

We will also learn about the Cloud Native Computing Foundation (CNCF), which currently hosts the Kubernetes project, along with other popular cloud native projects, such as Argo, Cilium, Prometheus, Fluentd, etcd, CoreDNS, cri-o, containerd, Helm, Envoy, Istio, and Linkerd, just to name a few.

By the end of this chapter, you should be able to:

- Define Kubernetes.
- Explain the reasons for using Kubernetes.
- Discuss the features of Kubernetes.
- Discuss the evolution of Kubernetes from Borg.
- Explain the role of the Cloud Native Computing Foundation.

## What Is Kubernetes?

> "Kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications".

Kubernetes comes from the Greek word κυβερνήτης, which means helmsman or ship pilot. With this analogy in mind, we can think of Kubernetes as the pilot on a ship of containers.

Kubernetes is also referred to as k8s (pronounced Kate's), as there are 8 characters between k and s.

Kubernetes is highly inspired by the Google Borg system, a container and workload orchestrator for its global operations, Google has been using for more than a decade. It is an open source project written in the Go language and licensed under the License, Version 2.0.

Kubernetes was started by Google and, with its v1.0 release in July 2015, Google donated it to the Cloud Native Computing Foundation (CNCF), one of the largest sub-foundations of the Linux Foundation.

New Kubernetes versions are released in 4 month cycles. The current stable version is 1.29 (as of December 2023).

## From Borg to Kubernetes

According to the abstract of Google's Borg paper, published in 2015,

> "Google's Borg system is a cluster manager that runs hundreds of thousands of jobs, from many thousands of different applications, across a number of clusters each with up to tens of thousands of machines".

For more than a decade, Borg has been Google's secret, running its worldwide containerized workloads in production. Services we use from Google, such as Gmail, Drive, Maps, Docs, etc., are all serviced using Borg.

Among the initial authors of Kubernetes were Google employees who have used Borg and developed it in the past. They poured in their valuable knowledge and experience while designing Kubernetes. Several features/objects of Kubernetes that can be traced back to Borg, or to lessons learned from it, are:

- API servers
- Pods
- IP-per-Pod
- Services
- Labels.

We will explore all of them, and more, in this course.

## Kubernetes Features

Kubernetes offers a very rich set of features for container orchestration. Some of its fully supported features are:

- Automatic bin packing

    Kubernetes automatically schedules containers based on resource needs and constraints, to maximize utilization without sacrificing availability.

- Designed for extensibility

    A Kubernetes cluster can be extended with new custom features without modifying the upstream source code.

- Self-healing

    Kubernetes automatically replaces and reschedules containers from failed nodes. It terminates and then restarts containers that become unresponsive to health checks, based on existing rules/policy. It also prevents traffic from being routed to unresponsive containers.

- Horizontal scaling

    Kubernetes scales applications manually or automatically based on CPU or custom metrics utilization.

- Service discovery and load balancing

    Containers receive IP addresses from Kubernetes, while it assigns a single Domain Name System (DNS) name to a set of containers to aid in load-balancing requests across the containers of the set.

Additional fully supported Kubernetes features are:

- Automated rollouts and rollbacks

    Kubernetes seamlessly rolls out and rolls back application updates and configuration changes, constantly monitoring the application's health to prevent any downtime.

- Secret and configuration management

    Kubernetes manages sensitive data and configuration details for an application separately from the container image, in order to avoid a rebuild of the respective image. Secrets consist of sensitive/confidential information passed to the application without revealing the sensitive content to the stack configuration, like on GitHub.

- Storage orchestration

    Kubernetes automatically mounts software-defined storage (SDS) solutions to containers from local storage, external cloud providers, distributed storage, or network storage systems.

- Batch execution

    Kubernetes supports batch execution, long-running jobs, and replaces failed containers.

- IPv4/IPv6 dual-stack

    Kubernetes supports both IPv4 and IPv6 addresses.

Kubernetes supports common Platform as a Service specific features such as application deployment, scaling, and load balancing, but allows users to integrate their desired monitoring, logging and alerting solutions through optional plugins.

There are many additional features currently in alpha or beta phase. They will add great value to any Kubernetes deployment once they become stable features. For example, support for role-based access control (RBAC) is stable only as of the Kubernetes 1.8 release, while cronjob support is stable only as of release 1.21.

## Why Use Kubernetes?

Another one of Kubernetes' strengths is portability. It can be deployed in many environments such as local or remote Virtual Machines, bare metal, or in public/private/hybrid/multi-cloud setups.

Kubernetes extensibility allows it to support and to be supported by many 3rd party open source tools which enhance Kubernetes' capabilities and provide a feature-rich experience to its users. It's architecture is modular and pluggable. Not only does it orchestrate modular, decoupled microservices type applications, but also its architecture follows decoupled microservices patterns. Kubernetes' functionality can be extended by writing custom resources, operators, custom APIs, scheduling rules or plugins.

For a successful open source project, the community is as important as having great code. Kubernetes is supported by a thriving community across the world. It has more than 3,500 contributors, who, over time, have pushed over 120,000 commits. There are meet-up groups in different cities and countries which meet regularly to discuss Kubernetes and its ecosystem. The community is divided into Special Interest Groups (SIGs), groups which focus on special topics, such as scaling, bare metal, networking, storage, etc. We will learn more about them in our last chapter, "Kubernetes Community".

## Cloud Native Computing Foundation (CNCF)

The Cloud Native Computing Foundation (CNCF) is one of the largest sub-projects hosted by the Linux Foundation. CNCF aims to accelerate the adoption of containers, microservices, and cloud-native applications.

CNCF hosts a multitude of projects, with more to be added in the future. CNCF provides resources to each of the projects, but, at the same time, each project continues to operate independently under its pre-existing governance structure and with its existing maintainers. Projects within CNCF are categorized based on their maturity levels: Sandbox, Incubating, and Graduated. At the time of this writing, over a dozen projects had reached Graduated status with many more Incubating and in the Sandbox.

Popular graduated projects (as of March 2024):

- Kubernetes container orchestrator
- Argo workflow engine for Kubernetes
- etcd distributed key-value store
- CoreDNS DNS server
- containerd container runtime
- CRI-O container runtime
- Envoy cloud native proxy
- Fluentd for unified logging
- Flux continuous delivery for Kubernetes
- Harbor registry
- Helm package management for Kubernetes
- Linkerd service mesh for Kubernetes
- Open Policy Agent policy engine
- Prometheus monitoring system and time series DB
- Rook cloud native storage orchestrator for Kubernetes

Key incubating projects:

- Buildpacks.io builds application images
- Contour ingress controller for Kubernetes
- gRPC for remote procedure call (RPC)
- CNI for Linux containers networking
- Knative serverless containers in Kubernetes
- KubeVirt Kubernetes based Virtual Machine manager
- Notary for data security
- [And many more.](https://www.cncf.io/projects/)

There are many dynamic projects in the CNCF Sandbox geared towards metrics, monitoring, identity, scripting, serverless, nodeless, edge, expecting to achieve Incubating and possibly Graduated status. While many active projects are preparing for takeoff, others are being archived once they become less active and no longer in demand. The first projects to be archived are the rkt container runtime, the distributed OpenTracing, Brigade event driven automation tool, and Service Mesh Interface.

The projects under CNCF cover the entire lifecycle of a cloud native application, from its execution using container runtimes, to its monitoring and logging. This is very important to meet the goals of CNCF.

## CNCF and Kubernetes

For Kubernetes, the Cloud Native Computing Foundation:

- Provides a neutral home for the Kubernetes trademark and enforces proper usage.
- Provides license scanning of core and vendor code.
- Offers legal guidance on patent and copyright issues.
- Creates and maintains open source learning curriculum, training, and certification for Kubernetes and cloud native associates (KCNA), Kubernetes administrators (CKA), Kubernetes application developers (CKAD), Kubernetes security specialists (CKS), and more.
- Manages a software conformance working group.
- Actively markets Kubernetes.
- Supports ad hoc activities.
- Sponsors conferences and meetup events.

# 05. Kubernetes Architecture

In this chapter, we will explore the Kubernetes architecture, the components of a control plane node, the role of the worker nodes, the cluster state management with etcd and the network setup requirements. We will also learn about the Container Network Interface (CNI), as Kubernetes' network specification.

By the end of this chapter, you should be able to:

- Discuss the Kubernetes architecture.
- Explain the different components of the control plane and worker nodes.
- Discuss cluster state management with etcd.
- Review the Kubernetes network setup requirements.

## Kubernetes Architecture

At a very high level, Kubernetes is a cluster of compute systems categorized by their distinct roles:

- One or more control plane nodes
- One or more worker nodes (optional, but recommended).

![alt text](02.png "Components of the Kubernetes Cluster")

_Components of the Kubernetes Cluster_

## Control Plane Node Overview

The control plane node provides a running environment for the control plane agents responsible for managing the state of a Kubernetes cluster, and it is the brain behind all operations inside the cluster. The control plane components are agents with very distinct roles in the cluster's management. In order to communicate with the Kubernetes cluster, users send requests to the control plane via a Command Line Interface (CLI) tool, a Web User-Interface (Web UI) Dashboard, or an Application Programming Interface (API).

It is important to keep the control plane running at all costs. Losing the control plane may introduce downtime, causing service disruption to clients, with possible loss of business. To ensure the control plane's fault tolerance, control plane node replicas can be added to the cluster, configured in High-Availability (HA) mode. While only one of the control plane nodes is dedicated to actively managing the cluster, the control plane components stay in sync across the control plane node replicas. This type of configuration adds resiliency to the cluster's control plane, should the active control plane node fail.

To persist the Kubernetes cluster's state, all cluster configuration data is saved to a distributed key-value store which only holds cluster state related data, no client workload generated data. The key-value store may be configured on the control plane node (stacked topology), or on its dedicated host (external topology) to help reduce the chances of data store loss by decoupling it from the other control plane agents.

In the stacked key-value store topology, HA control plane node replicas ensure the key-value store's resiliency as well. However, that is not the case with external key-value store topology, where the dedicated key-value store hosts have to be separately replicated for HA, a configuration that introduces the need for additional hardware, hence additional operational costs.

## Control Plane Node Components

A control plane node runs the following essential control plane components and agents: API server, scheduler, controller managers, and key-value data store.

In addition, the control plane node runs: container runtime, node agent (kubelet), proxy (kube-proxy), optional add-ons for observability, such as dashboard, cluster-level monitoring, and logging.

Components

#### API Server

All the administrative tasks are coordinated by the kube-apiserver, a central control plane component running on the control plane node. The API Server intercepts RESTful calls from users, administrators, developers, operators and external agents, then validates and processes them. During processing the API Server reads the Kubernetes cluster's current state from the key-value store, and after a call's execution, the resulting state of the Kubernetes cluster is saved in the key-value store for persistence. The API Server is the only control plane component to talk to the key-value store, both to read from and to save Kubernetes cluster state information - acting as a middle interface for any other control plane agent inquiring about the cluster's state.

The API Server is highly configurable and customizable. It can scale horizontally, but it also supports the addition of custom secondary API Servers, a configuration that transforms the primary API Server into a proxy to all secondary, custom API Servers, routing all incoming RESTful calls to them based on custom defined rules

#### Scheduler

The role of the kube-scheduler is to assign new workload objects, such as pods encapsulating containers, to nodes - typically worker nodes. During the scheduling process, decisions are made based on current Kubernetes cluster state and new workload object's requirements. The scheduler obtains from the key-value store, via the API Server, resource usage data for each worker node in the cluster. The scheduler also receives from the API Server the new workload object's requirements which are part of its configuration data. Requirements may include constraints that users and operators set, such as scheduling work on a node labeled with disk==ssd key-value pair. The scheduler also takes into account Quality of Service (QoS) requirements, data locality, affinity, anti-affinity, taints, toleration, cluster topology, etc. Once all the cluster data is available, the scheduling algorithm filters the nodes with predicates to isolate the possible node candidates which then are scored with priorities in order to select the one node that satisfies all the requirements for hosting the new workload. The outcome of the decision process is communicated back to the API Server, which then delegates the workload deployment with other control plane agents.

The scheduler is highly configurable and customizable through scheduling policies, plugins, and profiles. Additional custom schedulers are also supported, then the object's configuration data should include the name of the custom scheduler expected to make the scheduling decision for that particular object; if no such data is included, the default scheduler is selected instead.

A scheduler is extremely important and complex in a multi-node Kubernetes cluster, while in a single-node Kubernetes cluster possibly used for learning and development purposes, the scheduler's job is quite simple.

#### Controller Managers

The controller managers are components of the control plane node running controllers or operator processes to regulate the state of the Kubernetes cluster. Controllers are watch-loop processes continuously running and comparing the cluster's desired state (provided by objects' configuration data) with its current state (obtained from the key-value store via the API Server). In case of a mismatch, corrective action is taken in the cluster until its current state matches the desired state.

The kube-controller-manager runs controllers or operators responsible to act when nodes become unavailable, to ensure container pod counts are as expected, to create endpoints, service accounts, and API access tokens.

The cloud-controller-manager runs controllers or operators responsible to interact with the underlying infrastructure of a cloud provider when nodes become unavailable, to manage storage volumes when provided by a cloud service, and to manage load balancing and routing.

#### Key-value Data Store

etcd is an open source project under the Cloud Native Computing Foundation (CNCF). etcd is a strongly consistent, distributed key-value data store used to persist a Kubernetes cluster's state. New data is written to the data store only by appending to it, data is never replaced in the data store. Obsolete data is compacted (or shredded) periodically to minimize the size of the data store.

Out of all the control plane components, only the API Server is able to communicate with the etcd data store.

etcd's CLI management tool - etcdctl, provides snapshot save and restore capabilities which come in handy especially for a single etcd instance Kubernetes cluster - common in Development and learning environments. However, in Stage and Production environments, it is extremely important to replicate the data stores in HA mode, for cluster configuration data resiliency.

Some Kubernetes cluster bootstrapping tools, such as kubeadm, by default, provision stacked etcd control plane nodes, where the data store runs alongside and shares resources with the other control plane components on the same control plane node.

![alt text](03.png "HA Stacked etcd")

_Stacked etcd Topology_

For data store isolation from the control plane components, the bootstrapping process can be configured for an external etcd topology, where the data store is provisioned on a dedicated separate host, thus reducing the chances of an etcd failure.

![alt text](04.png "External etcd")

_External etcd Topology_

Both stacked and external etcd topologies support HA configurations. etcd is based on the Raft Consensus Algorithm which allows a collection of machines to work as a coherent group that can survive the failures of some of its members. At any given time, one of the nodes in the group will be the leader, and the rest of them will be the followers. etcd gracefully handles leader elections and can tolerate node failure, including leader node failures. Any node can be treated as a leader.

Keep in mind however, that the leader/followers hierarchy is distinct from the primary/secondary hierarchy, meaning that neither node is favored for the leader role, and neither node outranks other nodes. A leader will remain active until it fails, at which point in time a new leader is elected by the group of healthy followers.

![alt text](05.png "Leader and Followers")

_Leader and Followers_

etcd is written in the Go programming language. In Kubernetes, besides storing the cluster state, etcd is also used to store configuration details such as subnets, ConfigMaps, Secrets, etc.

## Worker Node Overview

A worker node provides a running environment for client applications. These applications are microservices running as application containers. In Kubernetes the application containers are encapsulated in Pods, controlled by the cluster control plane agents running on the control plane node. Pods are scheduled on worker nodes, where they find required compute, memory and storage resources to run, and networking to talk to each other and the outside world. A Pod is the smallest scheduling work unit in Kubernetes. It is a logical collection of one or more containers scheduled together, and the collection can be started, stopped, or rescheduled as a single unit of work.

Also, in a multi-worker Kubernetes cluster, the network traffic between client users and the containerized applications deployed in Pods is handled directly by the worker nodes, and is not routed through the control plane node.

