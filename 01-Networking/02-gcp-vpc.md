### **Chapter 2: Google Cloud VPC**

#### **1. Introduction to Google Cloud VPC**
- **What is a VPC?**
  - A **Virtual Private Cloud (VPC)** is a private network within Google Cloud that allows you to launch Google Cloud resources such as virtual machine instances (VMs) and containers. It provides full control over networking, including IP allocation, routing, and network security.
  - A VPC spans across multiple Google Cloud regions and is isolated from other VPCs, offering secure communication for your resources.

- **Key Components of Google Cloud VPC:**
  - **Subnets**: A VPC is divided into **subnets** that define IP address ranges for regions. Subnets can be regional or global (for certain services like load balancing).
  - **Routes**: VPCs use **routes** to determine how traffic moves between networks, whether internal or external.
  - **Firewall Rules**: Google Cloud VPC allows you to set **firewall rules** to control traffic between different services, subnets, and external networks.

#### **2. Setting Up a Google Cloud VPC**
- **Creating a VPC**:
  - A VPC is created through the **Google Cloud Console**, **Cloud SDK**, or **Terraform**.
  - Basic steps:
    1. Navigate to the VPC section in Google Cloud Console.
    2. Choose **Create VPC** and select either **Auto Mode** or **Custom Mode**.
       - **Auto Mode**: Automatically creates subnets for each region.
       - **Custom Mode**: You define the subnets and IP address ranges.
    3. Set IP range and name your VPC.
    4. Set up **Firewall Rules** (default ones are applied, but you can modify them based on your requirements).

- **Subnets in VPC**:
  - A VPC can have multiple **subnets**, each within a different region, and each subnet has its own IP address range.
  - **Subnet IP ranges** should be within the **VPC’s IP range**.
  - **Private vs Public Subnets**: Public subnets typically have access to the internet through a **NAT Gateway** or **Internet Gateway**.
  
  **Hands-On**:  
  1. Create a **VPC** in Google Cloud Console.
  2. Add subnets in different regions.

#### **3. VPC Routing and IP Management**
- **Routes**:
  - Google Cloud automatically configures routes to allow communication between instances within a VPC.
  - You can also create custom routes to direct traffic to specific destinations (for example, routing traffic to another VPC or on-prem network).
  
  **Types of Routes**:
  - **Dynamic Routes**: Managed by Cloud Router, typically used for BGP (Border Gateway Protocol) routing in hybrid networks.
  - **Static Routes**: Manually configured routes to direct traffic based on destination IP ranges.

- **IP Addressing**:
  - A **VPC network** is defined by a CIDR block of IP addresses.
  - **Internal IP addresses** are used within a VPC.
  - **External IP addresses** are used for communication with the public internet.

  **Hands-On**:  
  1. Create custom routes and test communication between different subnets.
  2. Explore the IP allocation for your VPC.

#### **4. VPC Peering and Interconnecting VPCs**
- **VPC Peering**:
  - **VPC Peering** allows you to connect two VPCs in the same or different projects to enable internal communication between them.
  - Once VPC peering is established, you can share IP ranges and routes between the peered networks.
  
  **Limitations of VPC Peering**:
  - VPC peering does not allow transitive routing (you cannot route traffic through a third VPC).
  - Each peered VPC requires its own unique IP ranges.

  **Hands-On**:  
  1. Set up VPC peering between two projects in GCP.
  2. Test communication between VMs in different VPCs.

- **Interconnect**:
  - **Interconnect** provides high-bandwidth, low-latency connections between your on-premises network and Google Cloud VPC.
  - **Dedicated Interconnect** and **Partner Interconnect** offer dedicated connections to GCP.

#### **5. VPC Firewall Rules and Security**
- **Firewall Rules**:
  - Google Cloud allows you to set up **firewall rules** that control the traffic flow to and from your VM instances.
  - Rules can be based on IP ranges, tags, or service accounts.
  
  **Default Firewall Rules**: GCP automatically creates default firewall rules that allow inbound traffic on ports like SSH (22), RDP (3389), and ICMP for VM instances.
  
  **Creating Custom Firewall Rules**:
  - Create rules for specific traffic types, for example, only allowing HTTP/HTTPS traffic (ports 80, 443) to certain instances.
  
  **Hands-On**:  
  1. Create custom firewall rules to allow or deny traffic to/from specific instances.
  2. Apply firewall rules using tags or service accounts.

#### **6. Private Google Access**
- **Private Google Access**:
  - This allows **VM instances in a private subnet** to access Google Cloud services (like Google APIs) over internal IPs, without needing an external IP.
  
  **Use Case**: You can have VMs with no external IPs in private subnets while still accessing Google Cloud resources securely.

  **Hands-On**:  
  1. Enable Private Google Access on your subnets.
  2. Test access from a private instance to Google APIs.

#### **7. VPC Network Monitoring and Logging**
- **VPC Flow Logs**:
  - **VPC Flow Logs** provide visibility into network traffic within your VPC. This allows you to monitor ingress and egress traffic to detect anomalies and optimize performance.
  
- **Network Intelligence Center**:
  - This tool helps you analyze your VPC’s performance and provides insights into issues like connectivity or network security.

  **Hands-On**:  
  1. Enable VPC Flow Logs and analyze the data.
  2. Use Network Intelligence Center to troubleshoot network performance.

---

### **Advanced Concepts**

#### **1. Advanced Routing with Cloud Router**
- Cloud Router is used for **dynamic routing** between Google Cloud VPCs and on-premises networks, particularly when BGP is used. It enables **automatic route propagation**.
  
  **Hands-On**:
  1. Set up **Cloud Router** for BGP routing in a hybrid network.
  2. Test dynamic route updates with Cloud Router.

#### **2. VPC Shared Services**
- **Shared VPC** allows multiple projects within an organization to share the same VPC, which is managed centrally.
- Useful for managing network security and addressing large-scale multi-project environments.

#### **3. Multi-Region VPC Setup**
- Google Cloud VPCs are global, meaning you can create subnets in different regions and use global resources like **Global Load Balancing**.
  
  **Hands-On**:
  1. Set up a VPC with subnets in multiple regions and test cross-region communication.

#### **4. Transit Gateway and Hybrid Connectivity**
- A **Transit Gateway** helps you connect multiple VPCs or on-prem networks together.
- This is ideal for large, multi-cloud or hybrid cloud architectures.

---

### **Conclusion and Hands-On Labs**
After gaining a theoretical understanding of **Google Cloud VPC**, start implementing the concepts with **hands-on exercises**. The best way to learn this technology is by practicing in the **Google Cloud Console** or automating the setup with **Terraform**.

**Suggested Learning Path**:
1. Create a basic VPC with multiple subnets and practice routing.
2. Set up firewall rules for controlling traffic.
3. Implement VPC Peering and test communication between VPCs.
4. Explore advanced security features like Private Google Access.
5. Use **Cloud Router** for dynamic routing in hybrid networks.

---

### **Resources**
- [Google Cloud VPC Documentation](https://cloud.google.com/vpc/docs)
- [VPC Peering Documentation](https://cloud.google.com/vpc/docs/vpc-peering)
- [Cloud Router and BGP Routing](https://cloud.google.com/network-connectivity/docs/cloud-router)
- [Google Cloud Firewall Rules](https://cloud.google.com/vpc/docs/firewalls)
- [Private Google Access](https://cloud.google.com/vpc/docs/configure-private-google-access)
