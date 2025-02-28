### **Chapter 2: Load Balancer (External & Internal) and All Types Used in GCP**


#### **2.1. Introduction to Load Balancers**
- **What is a Load Balancer?**
  - A **Load Balancer** is a device or software that distributes incoming network or application traffic across multiple servers to ensure no single server becomes overwhelmed.
  - Load balancing helps ensure high availability, reliability, and scalability for applications by directing traffic to healthy instances.

- **Why Load Balancers are Important?**
  - They ensure high availability by distributing traffic across healthy instances.
  - Load balancers improve scalability by enabling applications to handle increased traffic without affecting performance.
  - They provide redundancy by rerouting traffic if an instance or region becomes unavailable.

---

#### **2.2. Types of Load Balancers in GCP**

Here’s an updated **tree structure** of the different types of load balancers in GCP:

```
Load Balancers in GCP
│
├── External Load Balancers
│   ├── Global External HTTP(S) Load Balancer
│   │   ├── SSL Offloading
│   │   ├── Content-Based Routing
│   │   └── Auto-scaling Backend Services
│   ├── External TCP/SSL Proxy Load Balancer
│   │   ├── SSL Termination
│   │   └── TCP-Based Load Balancing
│   ├── External UDP Load Balancer
│   │   └── Load Balancing for UDP Traffic
│   └── External Application Load Balancer (App Load Balancer)
│       ├── HTTP/HTTPS Traffic Routing
│       ├── URL-Based Routing
│       ├── Web Application Acceleration
│       └── SSL Termination
│
└── Internal Load Balancers
    ├── Internal HTTP(S) Load Balancer
    │   ├── HTTP(S) Traffic Routing within VPC
    │   └── Private Applications
    ├── Internal TCP/UDP Load Balancer
    │   ├── TCP/UDP Traffic Routing within VPC
    │   └── Non-HTTP Applications (Databases, APIs)
    └── Internal Application Load Balancer (App Load Balancer)
        ├── HTTP/HTTPS Traffic Routing
        ├── URL-Based Routing for Internal Traffic
        └── SSL Offloading for Internal Applications
```

---

#### **2.3. Basic Load Balancing Concepts**

1. **How Load Balancing Works**
   - **Traffic Distribution**: The load balancer receives incoming traffic, checks the health of the backend instances, and routes the requests based on health checks and load distribution algorithms.
   - **Load Balancing Algorithms**:
     - **Round Robin**: Distributes requests evenly across all instances.
     - **Least Connections**: Routes traffic to the server with the least active connections.
     - **Weighted Distribution**: Routes traffic based on server weights.

2. **Backend Services**
   - Backend services are groups of instances or containers that handle the application traffic. Load balancers direct traffic to these backend services.
   - **Health Checks**: Load balancers continuously monitor the health of backend services, ensuring traffic is only sent to healthy instances. If an instance fails, traffic is rerouted to healthy instances.

3. **Forwarding Rules**
   - Forwarding rules define how traffic is routed to backend services. They specify the IP address and protocol (HTTP, TCP, etc.) that incoming requests will use.

4. **Backend Pools**:
   - Backend pools contain the VM instances or containerized services that will handle incoming traffic.
   - In GCP, backend pools can be composed of **instance groups** or **managed instance groups (MIGs)** for automated scaling.

---

#### **2.4. Advanced Load Balancing Concepts**

1. **Global Load Balancing (External HTTP(S) Load Balancer)**
   - **Global Distribution**: The external HTTP(S) load balancer automatically distributes traffic across multiple global locations, ensuring that users are connected to the nearest and most responsive backend.
   - **Auto-Scaling**: Automatically adjusts the number of instances in the backend pool based on incoming traffic. This helps maintain optimal performance and efficiency.
   - **Content-Based Routing**: Routes requests based on the URL path or hostname. For example, you can route `/images` requests to one set of backends and `/api` requests to another.

2. **External Application Load Balancer (App Load Balancer)**
   - **Routing HTTP/HTTPS Traffic**: Handles web traffic (HTTP/HTTPS) efficiently, ideal for web applications and microservices.
   - **URL-Based Routing**: Routes traffic based on the URL path, enabling you to direct different types of requests (e.g., `/images`, `/api`) to different backend services.
   - **Web Application Acceleration**: Optimizes web traffic performance using caching, reducing latency for users.
   - **SSL Termination**: SSL connections are terminated at the load balancer, offloading the decryption task from backend services.
   - **Use Case**: Ideal for web applications where the traffic is HTTP/HTTPS-based, offering advanced traffic management and security features.

3. **Network Load Balancer (NLB)**
   - **Low-Latency, Regional Load Balancer**: The **Network Load Balancer** is a Layer 4 TCP/UDP load balancer that distributes non-HTTP traffic with low-latency requirements.
   - **Use Case**: Perfect for applications that require ultra-low latency and high throughput, such as gaming applications or real-time APIs.

4. **Internal Load Balancing for Private Traffic**
   - **Internal HTTP(S) Load Balancer**: Routes HTTP(S) traffic within the GCP VPC, making it ideal for microservices and other internal applications.
   - **Internal TCP/UDP Load Balancer**: Useful for applications that rely on TCP/UDP traffic, such as database clusters, internal APIs, and messaging systems.

---

#### **2.5. Use Case Scenarios**

1. **Public Website (External Load Balancer)**
   - **Scenario**: A global e-commerce website that serves users worldwide.
   - **Solution**: Use a **Global External HTTP(S) Load Balancer** to distribute incoming web traffic. It can route traffic based on URL paths and provide SSL offloading for secure connections.

2. **Internal Application (Internal Load Balancer)**
   - **Scenario**: A microservices architecture within a corporate network.
   - **Solution**: Use an **Internal HTTP(S) Load Balancer** to route traffic between private backend services deployed within the same VPC.

3. **Game Server or VoIP (External UDP Load Balancer)**
   - **Scenario**: A multiplayer online game server that uses UDP for communication.
   - **Solution**: Use an **External UDP Load Balancer** to distribute UDP traffic across multiple game servers.

4. **Database Cluster (Internal TCP/UDP Load Balancer)**
   - **Scenario**: A database cluster with multiple instances for high availability.
   - **Solution**: Use an **Internal TCP/UDP Load Balancer** to distribute traffic among database instances, ensuring that each query reaches a healthy database node.

5. **Web Application (App Load Balancer)**
   - **Scenario**: A web application that handles multiple types of traffic, such as image delivery, API calls, and static content.
   - **Solution**: Use an **External App Load Balancer** to route requests to different backends based on URL paths, ensuring optimized delivery of different types of content.

---

#### **2.6. Hands-On Tasks**
- **Task 1: Set Up External HTTP(S) Load Balancer**
  - Create a backend service using a managed instance group.
  - Configure a global external HTTP(S) load balancer to route traffic to the backend.
  - Enable SSL termination for secure connections.
  - Set up health checks and autoscaling.

- **Task 2: Configure Internal HTTP(S) Load Balancer**
  - Set up an internal HTTP(S) load balancer for routing private application traffic within a VPC.
  - Test routing between different services and ensure they are isolated from the internet.

- **Task 3: Implement External Application Load Balancer**
  - Set up an **App Load Balancer** for routing HTTP/HTTPS traffic to multiple backend services based on URL paths.
  - Enable SSL offloading and configure web application acceleration.

- **Task 4: Implement Health Checks and Auto-Scaling**
  - Set up health checks for backend services and test failover behavior.
  - Configure auto-scaling to automatically add or remove instances from the backend pool based on traffic load.

---

#### **2.7. Resources**
- **Google Cloud Load Balancing Documentation**:
  - [GCP Cloud Load Balancing Decision Tree](https://jayendrapatil.com/google-cloud-load-balancing-types/)
  - [GCP Load Balancing Overview](https://cloud.google.com/load-balancing/docs)
  - [External HTTP(S) Load Balancer](https://cloud.google.com/load-balancing/docs/https)
  - [External Application Load Balancer](https://cloud.google.com/load-balancing/docs/application)
  - [Network Load Balancer](https://cloud.google.com/load-balancing/docs/network)
  - [Internal HTTP(S) Load Balancer](https://cloud.google.com/load-balancing/docs/internal)
  - [Internal TCP/UDP Load Balancer](https://cloud.google.com/load-balancing/docs/internal)
---

