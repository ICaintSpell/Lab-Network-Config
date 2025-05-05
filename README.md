Home Lab Setup - JohnWesleyPaigeJr.com

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

🔐 pfSense Firewall Rules

General Rule Format

Interface

Action

Protocol

Source

Destination

Port

Description

Any

Block

*

RFC1918

WAN

*

Block private to WAN

VLAN 99 (Management)

Allow HP laptop (192.168.4.x) to access VLAN 99 services (WebGUI, SSH)

Block all other VLANs from accessing VLAN 99

VLAN 10 (LAN / User Devices)

Allow full outbound internet access

Allow DNS & DHCP

Allow access to Server VLAN for AD/DNS

VLAN 20 (IoT)

Allow internet access

Block access to all other VLANs (except specific ports to server if needed)

VLAN 30 (Cameras)

Allow NVR IP (on server VLAN) to access cameras (port 554 RTSP, 80 HTTP)

Block internet access (optional for security)

VLAN 40 (Servers)

Allow inbound from LAN for services

Allow outbound to internet

VLAN 50 (Guests)

Allow only internet access

Block internal VLANs

🔧 Domain Controller To-Do



🌍 Website (Ubuntu VM)



☁️ Azure Integration



This document is a living blueprint of the evolving Paige Home Lab. Configs and implementations are updated as new services come online.
