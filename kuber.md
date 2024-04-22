### Kubernetes Details

1. Control Plane
   - API Server
     - This is the front desk of kubernetes. whenever we try to connect to any pods or service, it all goes through API server.
   - etcd (Persistence)
     - Its like a database storing data of running containers, pods and pods details and which pods are which part of containers etc.
   - Scheduler
     - Its a like an event planner for our containers. It decides which Node will run in which container and decides on resource availability, other constraints etc
   - Control Manager
     - Control Managers are there to verify if all the contianers are running smoothly. If something goes off then they try to fix it itself.
   - Cloud Controller Manager
     - This allows kubernetes to interact with the cloud providers like aws, azure. It helps in load balancing and persistent storage etc.
2. Worker Nodes
   - Kubelet
     - Its called manager for all working nodes. It ensures that all the working nodes are running properly as they should.
   - kube-proxy
     - Its a network proxy that runs on each node in a Kubernetes cluster. Its reponsible for maintaining network connectivity betweeen services and pods.
   - Container Runtime
     - It's the software that is responsible for managing execution and execution of the containers within the Kubernetes environment. Kubernetes supports container runtimes such as `containerd, CRI-O or other type of CRI(Container Runtime Interface)`
3. Other Components
   - Pods
     - This is the smallest unit in Kubernetes, Pod is a group of one or more contianers
   - Service
     - Its like a phone directory for pods. Since pods can come and go service provides a stable address so that other parts of our application can find them.
   - Volume
     - Volume is like an external hard-drive that can be attached to a Pod to store data.
   - Name space
     - Its a way to divide cluster resources among multiple users or teams. It's like having different folders on a shared computer.
   - Ingress
     - Its like a front door for external access to your applications, controlling how HTTP & HTTPs traffic should be routed to our service.

<!-- VMs vs Contrainers -->

- Virtual Machines run all the components including their own operating system on top of the virtualized hardware.

<!-- Container deployments -->

    - Containers are similar to VMs but they do have their flexibility to share operating system among applications. Containers are more lightweight and they have their own filesystem, sharing of CPUs, memory, process space etc. They are decoupled from the underlying infrastructure, they are portable across clouds and OS distributions.

2. Containers have become popular because of

   - Agile application creation and deployment
     - Increased ease and efficiency of container image creation compared to VMs.
   - Continuous development & Integration & deployment
     - Provides for reliable and frequent container image build and deployments with quick rollbacks
   - Observability
     - It can monitor OS-level and application health and other signals
   - Environmental consistency
     - development, testing and pproduction can run the same on a laptop as it does in the cloud.
   - Cloud & OS distribution
     - Ubuntu, RHEL, coreOS
   - Application centric management
     - level of abstraction from running an application on an OS to using logical resources.
   - Loose coupled
     - applications are broken into smaller pieces and can be deployed and managed dynamically.
   - Resource isolation
     - predictable application performance
   - Resource utilization
     - high efficiency and density
       **_why do we need kubernetes ?_**
   - If one container goes down another container needs to start.
   - kubernetes provides us with a framework to run distributed systems resiliently. Kubernetes can manage failover and do scaling for our applications.

## Kubernetes provides use with:

    - Service dicovery & Load balancing
        - Kubernetes exposes a container using DNS Name or IP address. If the traffic is high for the container, then it does load balancing itself and distributes the traffic so the deployment is stable
    - storage Orchestration
        - Kubernetes provides us with flexibility to choose storage system of our choice, such as local storage or cloud storage.
    - Automated rollouts and rollbacks
        - we can specify our requirements for the container and we can automate kubernetes to create new containers for our deployment, removing existing containers and adopt all new containers resources to current container
    - Automatic bin packing
        - we provide kubernetes with a cluster of nodes that it can use to run the tasks. we can decide the size of the container of kubernetes and it can fit the application accordingly by using the containerization as best way possible.
    - Self healing
        - The best thing about kubernetes is that it has self healing process where it can reboot, kill or even diagnose any container that doesn't responds to clients use. And kubernetes will not notify about it to the client until the containers are fully ready to serve.
    - Secret and Configuration Management
        - Kubernetes let us store and manage store sensitive informations.
    - Batch Execution
    - Horizontal Scaling
        - wew can scale our application Horizontally even with one command or automatically based on CPU usage.
    - IPv4 / IPv6 dual-stack
        - Allocation of IPv4 and IPv6 addresses to pods
    - Designed for Extensibility
        - Adding features to our kubernetes cluster without chainging source code.

- If any type of application can run in a container then it will run seamlessly on Kubernetes Container

### Setting Up kubernetes with EC2
