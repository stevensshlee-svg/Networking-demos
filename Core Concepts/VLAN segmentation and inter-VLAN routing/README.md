# VLAN Segmentation and Inter-VLAN Routing
VLAN segmentation and Inter-VLAN routing via Router on a stick (ROAS) configuration

## Overview
Implemented VLAN-based network segmentation and enabled communication between VLANs using router-on-a-stick trunking and subinterfaces.

## VLAN Design
* VLAN 10: Users - 192.168.10.0/24
* VLAN 20: IT - 192.168.20.0/24

## Key Tasks
* Created VLANs for each department and assigned the proper switch access ports
* Configured the native VLAN to an unused VLAN
* Configured 802.1q trunk encapsulation between the router and the switch
* Implemented router subinterfaces as default gateways
* Verified inter-VLAN communication
  
## Screenshot
<img width="628" height="551" alt="network topology" src="https://github.com/user-attachments/assets/49a10131-462c-4932-8803-06c6de2e553e" />
<img width="677" height="307" alt="vlans" src="https://github.com/user-attachments/assets/bde93174-a319-4224-9fa9-374a3d9f70b5" />
<img width="696" height="706" alt="switchport configs" src="https://github.com/user-attachments/assets/a7bac350-ce21-42e5-98f5-4d74acbac8d9" />
<img width="696" height="671" alt="router subinterfaces" src="https://github.com/user-attachments/assets/97ac3a82-5db4-4cab-a903-75f19afa28cf" />
<img width="693" height="701" alt="test ping" src="https://github.com/user-attachments/assets/92b79a94-32f9-4ea3-8dea-5f63447ce048" />
