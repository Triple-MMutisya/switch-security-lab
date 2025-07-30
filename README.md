# switch-security-lab
# 🔐 Securing Cisco Switch Management Access

## 🔧 Description
This project demonstrates key techniques for securing Cisco switch management, including:
- Enabling SSH and disabling Telnet
- Configuring port security
- Isolating switch management via VLAN 99

## 🖥️ Lab Topology
- 1 Cisco switch
- 4 PCs (Admin PC on VLAN 99, others on VLANs 10 & 20)
- Separate VLAN for management interface
- Port security configured on all access ports

## 🚀 Configuration Summary

### SSH Setup:
- Created RSA keys
- Enabled SSH version 2
- Used `login local` and strong credentials

### Port Security:
- One MAC per port
- Sticky MAC enabled
- Shutdown on violation

### VLAN Management:
- VLAN 99 for management
- Management interface IP: 192.168.99.10

## 🗃️ Files Included
- `.gns3project` file
- Configuration `.cfg` files
- Topology image
- README.md

