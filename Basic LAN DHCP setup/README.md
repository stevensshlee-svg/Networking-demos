# Basic LAN DHCP setup
A simple LAN DHCP configuration deployment via Cisco Packet Tracer

## Overview
Designed and implemented a simple single-LAN network to demonstrate foundational Layer 1-3 connectivity, router interface configuration, and DHCP address assignment

## Topology and Configurations
Devices
* 1 Router
* 1 Switch
* 3 End Hosts

Configurations
* Network Address: 192.168.1.0 255.255.255.0 (/24)
* Excluded Address: 192.168.1.1 - 192.168.1.10
* Default-router: 192.168.1.1
* DNS-Server: 1.1.1.1
* Domain-name: test.lab

## Key Tasks
* Configured router LAN interface and the router to perform DHCP services
* Assgined automatic IP addressing to end devices
* Confirmed connectivity via ping tests

## Screenshots
<img width="652" height="556" alt="basic-lan-dhcp-config" src="https://github.com/user-attachments/assets/632e5d02-a661-43f3-9cbc-9005a0b4002d" />
<img width="689" height="693" alt="dhcp-config" src="https://github.com/user-attachments/assets/66a3abdb-db2c-4548-a90e-cf37dc390ecb" />
<img width="682" height="679" alt="pc0 config" src="https://github.com/user-attachments/assets/af670681-3962-4c41-ae37-4eac0081976b" />
<img width="696" height="701" alt="pc1 config" src="https://github.com/user-attachments/assets/1190a031-0dc8-4b71-9908-2ab1f8e84e45" />
<img width="694" height="707" alt="pc2 config" src="https://github.com/user-attachments/assets/6f979193-22d9-400c-812c-f432f5b332ef" />
<img width="808" height="761" alt="ping" src="https://github.com/user-attachments/assets/49a79d74-3c7c-4ec0-8a6f-809c7708db8d" />
