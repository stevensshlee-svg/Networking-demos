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
<img width="628" height="551" alt="network topology" src="https://github.com/user-attachments/assets/9fbc24e5-0a48-4c64-b9ee-7b2d72762e27" />
<img width="677" height="307" alt="vlans" src="https://github.com/user-attachments/assets/a8227e6a-bc8c-4f98-8c7e-2c70f99ff68c" />
<img width="696" height="706" alt="switchport configs" src="https://github.com/user-attachments/assets/aa521f36-07c2-4786-88a5-e865e7a21c94" />
<img width="696" height="671" alt="router subinterfaces" src="https://github.com/user-attachments/assets/80139064-6a92-4267-a9d8-8ddbb6fd20b6" />
<img width="693" height="701" alt="test ping" src="https://github.com/user-attachments/assets/83822dae-603e-4384-80fd-efaca6223f55" />
