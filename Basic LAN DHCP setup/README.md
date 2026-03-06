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
<img width="652" height="556" alt="basic-lan-dhcp-config" src="https://github.com/user-attachments/assets/238f13cc-6301-4b6f-baad-6e75557f3ff9" />
<img width="689" height="693" alt="dhcp-config" src="https://github.com/user-attachments/assets/1ba09657-43b2-457d-abb5-9d50df7e09c1" />
<img width="682" height="679" alt="pc0 config" src="https://github.com/user-attachments/assets/b242aead-ac9d-4dd6-9115-65a530af84e2" />
<img width="696" height="701" alt="pc1 config" src="https://github.com/user-attachments/assets/73355d8b-3d0f-46b4-b3aa-803880ee8c34" />
<img width="694" height="707" alt="pc2 config" src="https://github.com/user-attachments/assets/7919cdab-8992-404c-aac8-ff3158bbafbc" />
<img width="808" height="761" alt="ping" src="https://github.com/user-attachments/assets/b8bae843-8a10-42bc-ae15-b7026383c86d" />
