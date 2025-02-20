# 🎯 GCP Networking - Interview Q&A

## 🔥 Basic Questions

### 1️⃣ What is a VPC in GCP?
A **VPC (Virtual Private Cloud)** is a logically isolated network that allows you to manage resources securely.

### 2️⃣ What is the difference between Auto and Custom VPC?
- **Auto-mode VPC**: Automatically creates subnets in all regions.
- **Custom-mode VPC**: Requires manual subnet creation.

### 3️⃣ What is the purpose of firewall rules in GCP?
Firewall rules control **inbound and outbound traffic** based on IPs, ports, and protocols.

---

## 🚀 Advanced Questions

### 4️⃣ What is Cloud NAT, and why is it used?
Cloud NAT allows **private VMs** to access the internet securely without exposing their internal IPs.

### 5️⃣ How does GCP Load Balancer work?
- **HTTP(S) Load Balancer**: Global, best for web apps.
- **TCP/UDP Load Balancer**: Regional, used for non-HTTP traffic.
- **Internal Load Balancer**: Routes traffic inside the VPC.

### 6️⃣ What is the difference between Cloud Interconnect and VPN?
- **Cloud Interconnect**: Dedicated **private** connection to GCP.
- **VPN**: Secure **encrypted** connection over public internet.

### 7️⃣ What is Shared VPC?
A **Shared VPC** allows multiple projects to share the same VPC network securely.

---

## 🎯 Scenario-Based Questions
### 8️⃣ A company needs hybrid connectivity between on-prem and GCP. Which option do they use?
- **Cloud Interconnect** (For high-speed, dedicated connection).
- **Cloud VPN** (For secure, encrypted connectivity).

### 9️⃣ How would you troubleshoot VPC network latency issues?
1. Check **Firewall Rules**.
2. Use **VPC Flow Logs** to analyze traffic.
3. Verify **Routing Table** and **NAT configuration**.

---

🚀 **Practice these questions daily for interview success!** ✅
