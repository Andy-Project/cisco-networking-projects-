# Small Office Network Design (Cisco Packet Tracer)

## 📌 Project Overview
This project simulates the design, configuration, and testing of a fully functional small office network using **Cisco Packet Tracer**.  
It includes VLAN segmentation for different departments, inter-VLAN routing, DHCP, DNS, FTP services, and wireless connectivity.

The goal was to create a realistic office network topology that follows best practices in IP addressing, subnetting, and service deployment.

---

## 🖥️ Network Topology
**Devices Used:**
- **Cisco 1941 Router** – Core router & DHCP server
- **Cisco 2960 Switch** – Core switch with VLAN segmentation
- **WRT300N Wireless Router** – Configured as a wireless access point (AP)
- **End Devices:**
  - 5 Desktop PCs
  - 1 Laptop
  - 1 Network Printer
  - 1 Server (DNS & FTP services)

---

## 🗂 VLAN & IP Structure

| VLAN ID | Department       | Subnet           | Gateway        | DHCP Range                  |
|--------:|-----------------|------------------|---------------|-----------------------------|
| 10      | Sales           | 192.168.10.0/24  | 192.168.10.1  | 192.168.10.50 – 192.168.10.254 |
| 20      | Marketing       | 192.168.20.0/24  | 192.168.20.1  | 192.168.20.50 – 192.168.20.254 |
| 25      | Office Server   | 192.168.25.0/24  | 192.168.25.1  | 192.168.25.11 – 192.168.25.254 |

---

## ⚙️ Key Configurations
- **VLAN Creation & Port Assignment**
  - VLAN 10: Sales Department
  - VLAN 20: Marketing Department
  - VLAN 25: Office Server
- **Inter-VLAN Routing** using subinterfaces on the router
- **DHCP Configuration** per VLAN, excluding static IP ranges
- **DNS Server** for internal name resolution (`server.local`, `printer.local`)
- **FTP Server** setup for file transfers
- **Wireless Access Point** configured with WPA2-PSK security

---

## 🔍 Testing & Verification
- **Ping Tests**: Verified connectivity within VLANs, between VLANs, and across wired/wireless networks
- **DNS Resolution**: Confirmed local hostname resolution
- **FTP Access**: Tested successful login and file transfer
- **Troubleshooting**:
  - Fixed incorrect IP addressing on VLAN ports
  - Updated DHCP DNS server settings to use internal server
  - Resolved VLAN trunking and access mode configuration issues

---

## 📂 Repository Contents
- `Office_Network_Setup.pdf` – Full documentation with step-by-step configuration & troubleshooting
- `Office_Network.pkt` – Cisco Packet Tracer project file
- `images/` – Network topology diagrams & screenshots

---

## 🛠 Tools Used
- Cisco Packet Tracer
- Cisco IOS CLI
- Command Prompts (`ping`, `nslookup`, `ftp`)

The file, where I documented everything step-by-step and showed the full process, is attached. 

