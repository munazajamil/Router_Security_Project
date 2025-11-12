# Secure Remote Access Configuration on Cisco Router (Telnet, SSH, Console & Enable Passwords)

## 📘 Project Overview
This project demonstrates how to secure a Cisco Router using multiple access control methods 
Like Console, Enable, Telnet, and SSH — within Cisco Packet Tracer.

## 🧠 Objective
To configure Router0 for secure local and remote management by applying password protection and SSH authentication.

## 🖥️ Network Topology
I droped 2 PCs, 2 cisco switches and 1 Router on Cisco packet tracer canvas, then connect them all via streight through cable wire.


### IP Addressing
| Device | Interface | IP Address | Subnet Mask | Gateway |
|---------|------------|-------------|--------------|----------|
| PC0 | NIC | 192.168.10.10 | 255.255.255.0 | 192.168.10.1 |
| Switch1 | VLAN1 | 192.168.10.2 | 255.255.255.0 | — |
| Router0 | G0/0/0 | 192.168.10.1 | 255.255.255.0 | — |
| Router0 | G0/0/1 | 192.168.20.1 | 255.255.255.0 | — |
| Switch2 | VLAN1 | 192.168.20.2 | 255.255.255.0 | — |
| PC1 | NIC | 192.168.20.10 | 255.255.255.0 | 192.168.20.1 |

---

## ⚙️ Configuration Commands i used in my lab;

### 1️⃣ Console Access
```bash
line console 0
 password cisco
 login

2️⃣ Enable Password
enable secret class

3️⃣ Telnet Access
line vty 0 4
 password telnet123
 login
 transport input telnet

4️⃣ SSH Access
hostname Router0
ip domain-name lab.local
crypto key generate rsa
username admin privilege 15 secret admin123
line vty 0 4
 login local
 transport input ssh

🔍 Verification Commands i try to cross check if security is successful or not.
show running-config
show ip ssh
show users


✅ Test Results i got in this Lab:

Console password worked
Enable password worked
Telnet login verified
SSH login verified (with username admin)

🧩 Tools Used
Cisco Packet Tracer
Windows 10 where packet tracer is running
Networking basics (CCNA level)

- Learning Outcomes

Router access control configuration
Difference between Telnet and SSH
Using “show” commands for verification
Network segmentation using IP subnets

This was my Lab walk thorugh for CCNA.

