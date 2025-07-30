# 🔐 Cisco Switch Hardening: Disabling Unused Services

## 🧾 Description

This project focuses on enhancing the security posture of a Cisco switch by **disabling unused or insecure services**. These configurations reduce the attack surface of the device, improve performance, and follow Cisco and general network security best practices.

All configurations were tested in **GNS3** using Cisco IOSv switch.

---

## 🧰 Tools & Technologies

- Cisco IOSv (Switch)
- GNS3 Network Simulator
- CLI (Command Line Interface)

---

## 🎯 Objectives

- Disable unnecessary network and system services
- Harden switch against unauthorized access and service misuse
- Save and verify secure configurations

---

## 🛡️ Disabled Services

| Service | Reason for Disabling |
|--------|----------------------|
| HTTP/HTTPS | Disables web-based GUI interface |
| CDP | Prevents neighbor discovery info leaks |
| TCP/UDP small servers | Legacy test/debug services |
| PAD | Rarely used protocol |
| Finger | User info exposure risk |
| Proxy ARP | Limits spoofing vectors |
| LLDP (optional) | Disable if not using in multi-vendor environments |
| Source routing | Prevents route injection attacks |
| Boot network | Prevents unwanted network boots |

---

## ⚙️ Configuration Commands

```bash
! Disable HTTP and HTTPS server
no ip http server
no ip http secure-server

! Disable CDP globally
no cdp run
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


! Disable source routing and proxy ARP
no ip source-route
interface vlan 1
 no ip proxy-arp

! Disable boot network config
no service config
no boot network

! Disable LLDP (optional)
no lldp run

! Disable CDP version advertisement
no cdp advertise-v2

! Disable unused interfaces
interface range fa0/11 - 24
 shutdown

! Encrypt passwords and set login banner
service password-encryption
banner motd # UNAUTHORIZED ACCESS IS PROHIBITED #
