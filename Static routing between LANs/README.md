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
<img width="834" height="488" alt="network topology" src="https://github.com/user-attachments/assets/ed6377b5-97ee-4247-8886-668384970ded" />
<img width="695" height="703" alt="LA dhcp" src="https://github.com/user-attachments/assets/c07a441f-e315-42ca-9b4d-5a614bc30145" />
<img width="695" height="698" alt="LA router config" src="https://github.com/user-attachments/assets/1b73d3d9-5885-4d0a-ae7a-5a29b8e5fe0c" />
<img width="692" height="699" alt="newyork dhcp" src="https://github.com/user-attachments/assets/fce3e735-8782-4f5e-a256-b386b362ddbf" />
<img width="689" height="702" alt="newyork router config" src="https://github.com/user-attachments/assets/15c7165e-1286-4040-a70f-c65b2fa95db8" />
<img width="690" height="701" alt="ping tracert test" src="https://github.com/user-attachments/assets/c73faa4a-a6b1-41c7-905f-320f98c45857" />
