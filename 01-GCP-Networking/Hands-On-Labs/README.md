# 🛠️ Hands-On Labs: GCP Networking

## 📌 Lab 1: Create a Custom VPC and Subnet
### **Objective**:  
Set up a **custom-mode VPC** with a subnet.

### **Steps**:
1. Open **Cloud Console** → Navigate to **VPC Network**.
2. Click **Create VPC Network** → Name it `custom-vpc`.
3. Select **Custom-mode** → Add a subnet:
   - **Subnet Name**: `custom-subnet`
   - **Region**: `us-central1`
   - **IP Range**: `10.0.0.0/24`
4. Click **Create**.

---

## 📌 Lab 2: Configure Firewall Rules
### **Objective**:  
Allow SSH and HTTP traffic to instances.

### **Steps**:
1. Open **Cloud Console** → Navigate to **VPC Firewall**.
2. Click **Create Firewall Rule**:
   - **Name**: `allow-ssh-http`
   - **Network**: `custom-vpc`
   - **Direction**: Ingress
   - **Target**: `All instances in network`
   - **Source IP**: `0.0.0.0/0`
   - **Protocols**: Allow `TCP:22, 80`
3. Click **Create**.

---

## 📌 Lab 3: Configure Cloud NAT
### **Objective**:  
Enable internet access for private instances.

### **Steps**:
1. Open **Cloud Console** → Navigate to **Cloud NAT**.
2. Click **Create NAT Gateway**:
   - **Name**: `nat-gateway`
   - **Region**: `us-central1`
   - **Network**: `custom-vpc`
   - **Subnets**: `custom-subnet`
3. Click **Create**.

---
🚀 Proceed to **Interview-QA.md** for practice questions.
