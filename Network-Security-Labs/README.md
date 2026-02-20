# Lab: Implementing Network Segmentation & Access Control (ACLs)

### 🛡️ Scenario
A corporate network required strict segmentation to prevent the Sales department from accessing sensitive Financial servers. This lab demonstrates how to use VLANs and Extended Access Control Lists (ACLs) to harden the network.

### 🛠️ Tools Used
* **Cisco IOS CLI**
* **Cisco Packet Tracer / GNS3**
* **Standard & Extended ACLs**

### 🔍 Configuration Steps
1. **Segmentation:** Created **VLAN 10 (Sales)** and **VLAN 20 (Finance)** to isolate broadcast domains.
2. **Inter-VLAN Routing:** Configured a Router-on-a-Stick model to allow controlled communication.
3. **Security Implementation:** Applied an **Extended ACL** on the Finance Gateway to deny all traffic from the Sales subnet while allowing specific IT admin access via SSH (Port 22).

### 📜 Key Cisco Commands Used
`access-list 101 deny ip 192.168.10.0 0.0.0.255 192.168.20.0 0.0.0.255`
`access-list 101 permit ip any any`
`interface GigabitEthernet0/0.20`
`ip access-group 101 in`

### 🏆 Outcome
Successfully blocked unauthorized cross-department communication, reducing the internal attack surface and ensuring compliance with the **Principle of Least Privilege**.
