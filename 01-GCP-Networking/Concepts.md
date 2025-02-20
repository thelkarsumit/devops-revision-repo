# GCP Networking - Key Concepts

## 🏗️ 1. Google Cloud Virtual Private Cloud (VPC)
- A **VPC** is a global network that allows you to define networking policies, including subnetting, routing, and firewalls.
- **VPC Features**:
  - Global scope: Subnets can span regions.
  - **Auto-mode VPC**: Default subnets are created automatically in each region.
  - **Custom-mode VPC**: You manually define subnets.

## 🔗 2. Subnets
- **Subnets** divide the VPC network into smaller addressable blocks.
- **Regional resources**: Subnets are region-specific but communicate via the global VPC.
- **CIDR Ranges**: Define the IP range (e.g., `10.0.0.0/24`).

## 🔥 3. Firewalls & Security
- **Firewall Rules** control inbound and outbound traffic.
- **Allow/Deny rules** specify which traffic is permitted or blocked.
- **Priority system**: Rules are processed based on priority (lowest first).

## 🛜 4. Load Balancing
- **Global and regional** load balancing available.
- **Types**:
  - HTTP(S) Load Balancer → Best for web traffic.
  - TCP/UDP Load Balancer → Suitable for network-based services.
  - Internal Load Balancer → Routes traffic inside the VPC.

## 🔄 5. NAT (Network Address Translation)
- **Cloud NAT** allows private VMs to access the internet securely without exposing internal IPs.

## 🌐 6. Hybrid Connectivity
- **Cloud Interconnect** → Dedicated connection between GCP and on-premises.
- **VPN** → Secure, encrypted connectivity.
- **Peering** → Direct connection between two VPC networks.

## 🛠️ 7. DNS, Private Google Access & Network Services
- **Cloud DNS**: Managed DNS service.
- **Private Google Access**: Allows private VMs to access Google APIs.
- **Service Networking**: Enables communication between VPCs.

---
🚀 Continue to **Hands-On-Labs/** to practice!
