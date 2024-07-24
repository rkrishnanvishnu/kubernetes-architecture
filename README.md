# kubernetes-architecture
Kubernetes Architecture
Control Plane (Master Node)

    API Server:
        The core component of Kubernetes.
        Accepts all incoming requests and exposes Kubernetes functionalities to the external world.
        Acts as the front-end for the Kubernetes control plane.

    etcd:
        A distributed key-value store.
        Stores all cluster-related information, including configuration data, state data, and metadata.

    Scheduler:
        Responsible for scheduling pods onto nodes.
        Receives information from the API server and assigns pods to appropriate nodes based on resource availability and other constraints.

    Controller Manager:
        Ensures that the desired state of the cluster matches the actual state.
        Manages controllers such as the ReplicaSet controller, Node controller, and others.

    Cloud Controller Manager:
        Integrates with cloud providers.
        Handles cloud-specific control logic, like managing load balancers, storage volumes, and more.

Data Plane (Worker Node)

    Kubelet:
        An agent that runs on each worker node.
        Ensures that the containers described in PodSpecs are running and healthy.
        Communicates with the API server to receive and execute pod specifications.

    Kube Proxy:
        Manages network connectivity and load balancing.
        Implements network rules to allow communication to your pods from network sessions inside or outside of your cluster.

    Container Runtime:
        The software that is responsible for running containers.
        Examples include Docker, containerd, CRI-O, etc.
        Executes the containers inside the pods and ensures they are running smoothly.
