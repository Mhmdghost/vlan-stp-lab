# VLAN + STP Lab using Cisco Packet Tracer

This project demonstrates how to build a segmented and loop-free network using VLANs and Spanning Tree Protocol (STP) with Cisco Packet Tracer.

## 🧰 Network Topology

- 3x Layer 2 Switches
- 2x Layer 3 (Multilayer) Switches
- 6 PCs across 3 VLANs:
  - VLAN 10 → PC0, PC4
  - VLAN 20 → PC1, PC3
  - VLAN 30 → PC2, PC5

## ⚙️ Features

- VLAN segmentation
- Trunk ports between switches
- Inter-VLAN Routing using Multilayer Switch
- Spanning Tree Protocol to prevent loops
- Manual port role definitions (Root, Designated)

## 📸 Topology Diagram

![Network Topology](vlan-lab.png)

## 📎 Included Files

- `vlan_project.pkt` – Packet Tracer file
- `vlan-lab.png` – Topology screenshot

## 🔧 CLI Configuration Commands

```bash
# Create VLANs
vlan 10
name "you name it"
vlan 20
name "you name it"
vlan 30
name "you name it"


# Assign ports to VLANs
interface " fa0/1 for example "
switchport mode access
switchport access vlan 10

interface "fa0/2 for example"
switchport mode access
switchport access vlan 20

interface "fa0/3 for example"
switchport mode access
switchport access vlan 30

# Configure trunk between switches
interface "fa0/12 for example"
switchport trunk encapsulation dot1q
switchport mode trunk

# Inter-VLAN Routing (on Multilayer Switch)
after that you need to assign ip addresses to all 
devices "pc's" from the GUI or CLi choose what u want 

# STP Configuration
spanning-tree vlan 10 priority 4096
spanning-tree vlan 20 priority 8192
spanning-tree vlan 30 priority 12288

**the priority start from 4096 ** (must be multiple of 4096)

# Verify STP and VLAN status
show spanning-tree
show vlan brief
show ip route
```

## ✅ Notes

- Packet Tracer version: 8.x or higher
- Ensure you configure trunk ports correctly
- Static IPs were assigned manually to each PC

## 👨‍💻 Author

Mohammed Waled  
🔗 [My Portfolio](https://portfolio-omega-lake-59.vercel.app)
