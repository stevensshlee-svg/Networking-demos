# Static routing between LANs
Configuring Inter-LAN connectivity using static routing

## Overview
Built a two-router topology to demonstrate Layer 3 routing between separate LANs using manually configured static routes

## Networks
* LAN A (Los Angeles): 192.168.10.0/24
* LAN B (New York): 192.168.20.0/24
* WAN Link: 10.0.0.0/30

## Key Tasks
* Configured DHCP on each router to provide end host connectivity within each LAN
* Configured router interfaces and WAN point-to-point link
* Created static routes to each LAN
* Validated packet flow using ping and tracert

## Screenshots
<img width="834" height="488" alt="network topology" src="https://github.com/user-attachments/assets/28f25f8b-bbc6-4dcc-81a1-50459da115f7" />
<img width="695" height="703" alt="LA dhcp" src="https://github.com/user-attachments/assets/2093063b-7eab-434e-935c-6d27a17882d5" />
<img width="695" height="698" alt="LA router config" src="https://github.com/user-attachments/assets/c1edfc5d-002f-45ec-81fa-21252285ddf6" />
<img width="692" height="699" alt="newyork dhcp" src="https://github.com/user-attachments/assets/69825fcd-dc41-421e-9abc-cde98e117bc9" />
<img width="689" height="702" alt="newyork router config" src="https://github.com/user-attachments/assets/4b1740bc-0d20-490c-8b94-7e33c52f6174" />
<img width="690" height="701" alt="ping tracert test" src="https://github.com/user-attachments/assets/d549d07e-410d-4d58-ae09-ae4c365a3858" />
