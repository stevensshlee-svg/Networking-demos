# DHCP per-VLAN & DNS-server
DHCP configuration per VLAN with a centralized DNS server


## Overview
Simulated an simple enterprise network topology using a Layer-3 switch for inter-VLAN routing, a router to provide centralized DHCP services, and a centralized DNS server to enable hostname-based communication across the network

## Network devices and topology
* 1 Router
* 1 Layer-3 Switch
* 1 DNS Server
* 4 End Hosts
* VLAN 10: Users - 192.168.1.0/24
* VLAN 20: IT - 192.168.2.0/24
* Router to L3 Switch: 10.0.0.0/30

## Key Tasks
### Layer-3 Switching
* Created VLANs and configured SVIs as the default gateway
* Enabled inter-VLAN routing on the switch
* Configured DHCP relay on each SVI to the router
### DHCP Services
* Created separate DHCP pools per VLAN on the router
* Assigned the correct default gateway (SVI ip) and distributed centralized DNS server address to all clients
### Routing
* Implemented a point-to-point network between router and the switch
* Added static routes on the router for VLAN return reachability
* Created a default route on the L3 switch to the router
### DNS
* Enabled DNS service on the network
* Created hostname entries for the DNS server and the router
* Verified name resolution across VLAN boundaries

## Screenshots
<img width="852" height="594" alt="network topology" src="https://github.com/user-attachments/assets/56b35bfa-27aa-4468-b997-db21847c3777" />
<img width="686" height="706" alt="svi" src="https://github.com/user-attachments/assets/d19e2c84-7de0-497a-92b9-aba927ba1be9" />
<img width="690" height="693" alt="switchport config" src="https://github.com/user-attachments/assets/216649d4-1856-4ae1-a40e-70e2efc3f8f8" />
<img width="691" height="704" alt="dhcp pool config" src="https://github.com/user-attachments/assets/6189a786-0d7b-4366-b5f3-4c91e4a19eb7" />
<img width="692" height="704" alt="int config + static routes" src="https://github.com/user-attachments/assets/dd524088-a578-44c5-aaae-9b71a71802f0" />
<img width="693" height="707" alt="user1 ip lease" src="https://github.com/user-attachments/assets/70d76c80-d428-4b18-81d9-88fd626fc624" />
<img width="694" height="706" alt="user1 gateway and dns" src="https://github.com/user-attachments/assets/790eaaf8-c469-4e00-961e-497c1b3ea22b" />
<img width="692" height="694" alt="it1 ip lease" src="https://github.com/user-attachments/assets/82f0e59f-f695-47fd-bed3-64e60f20bafd" />
<img width="686" height="701" alt="it1 dateway and dns" src="https://github.com/user-attachments/assets/05188f25-5fae-43c4-bdac-5202e0673c2b" />
<img width="688" height="705" alt="user2 ip lease" src="https://github.com/user-attachments/assets/95b1df01-2f78-4de4-a232-4546c5717a00" />
<img width="692" height="702" alt="user2 gateway and dns" src="https://github.com/user-attachments/assets/4d79914e-35cd-4dee-b4fb-1363ceab1adf" />
<img width="688" height="695" alt="it2 ip lease" src="https://github.com/user-attachments/assets/2c8d0896-2813-4a08-828d-b379326710c1" />
<img width="691" height="702" alt="it2 gateway and dns" src="https://github.com/user-attachments/assets/4115de48-8927-423c-94e2-71bd5a0dd92d" />
<img width="695" height="706" alt="a record" src="https://github.com/user-attachments/assets/1f070144-38eb-4292-9d8d-bb2c5f2ab067" />
<img width="691" height="704" alt="inter-vlan name resolution" src="https://github.com/user-attachments/assets/e6354979-fb78-4b13-b444-052b0515bbc0" />
