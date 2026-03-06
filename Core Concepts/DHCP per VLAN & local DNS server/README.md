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
<img width="852" height="594" alt="network topology" src="https://github.com/user-attachments/assets/b541c2e1-df9f-49aa-a5c7-fb9171a02905" />
<img width="686" height="706" alt="svi" src="https://github.com/user-attachments/assets/b06c5a03-8f8b-4e66-b2cf-645f30c8223e" />
<img width="690" height="693" alt="switchport config" src="https://github.com/user-attachments/assets/a6b31220-7c9e-42a9-9695-691d6279d987" />
<img width="691" height="704" alt="dhcp pool config" src="https://github.com/user-attachments/assets/5afb615f-cdf9-4513-9f21-a538ac28f942" />
<img width="692" height="704" alt="int config + static routes" src="https://github.com/user-attachments/assets/5fef52c7-81fb-44f4-8fbe-07c79058e0b4" />
<img width="693" height="707" alt="user1 ip lease" src="https://github.com/user-attachments/assets/c26a2060-3bc7-4495-8a74-0ced92210fcc" />
<img width="694" height="706" alt="user1 gateway and dns" src="https://github.com/user-attachments/assets/3f70bd92-88a4-4042-a6db-309af976bd88" />
<img width="692" height="694" alt="it1 ip lease" src="https://github.com/user-attachments/assets/9da5e1e6-0a97-4a46-a3f0-65289a29c8d3" />
<img width="686" height="701" alt="it1 dateway and dns" src="https://github.com/user-attachments/assets/7f4b8405-5679-4461-9c7f-2fef19f821a7" />
<img width="688" height="705" alt="user2 ip lease" src="https://github.com/user-attachments/assets/4cc3c05e-70a5-4004-8438-7a5e64da9641" />
<img width="692" height="702" alt="user2 gateway and dns" src="https://github.com/user-attachments/assets/516df385-121d-49a1-8fba-9c2f0d126c0d" />
<img width="688" height="695" alt="it2 ip lease" src="https://github.com/user-attachments/assets/862918cf-b250-468b-9ec0-d7ad5ea7efbe" />
<img width="691" height="702" alt="it2 gateway and dns" src="https://github.com/user-attachments/assets/96cdada8-2292-4ced-8827-9f37054a9340" />
<img width="695" height="706" alt="a record" src="https://github.com/user-attachments/assets/99cee89a-9e81-4c76-acab-ac08609e44f3" />
<img width="691" height="704" alt="inter-vlan name resolution" src="https://github.com/user-attachments/assets/b32d0edd-c595-4e78-bb1c-5933b02cb70c" />
