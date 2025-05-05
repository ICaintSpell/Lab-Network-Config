🧱 Core Infrastructure Overview

Primary Server: Dell XPS 420

Hypervisor: Windows Server 2019 (with Ubuntu VM for web hosting)

Domain: johnwesleypaigejr.com

Domain Controller Role: Configured and promoted

DNS: Installed and hosting internal zone

Firewall: Jetway + pfSense

🌐 Network Design

Subnets by Jetway Port:

Port 1 (WAN): ISP Uplink

Port 2: 192.168.2.0/24 – Core LAN (XPS420 Server/DC)

Port 3: 192.168.3.0/24 – Switch → Cameras, AP, Xbox, IoT devices

Port 4: 192.168.4.0/24 – Daily Driver (HP Laptop via HP Hub)

VLANs:

VLAN 10: LAN (User Devices)

VLAN 20: IoT Devices

VLAN 30: Cameras

VLAN 40: Servers

VLAN 50: Guest

VLAN 99: Management
