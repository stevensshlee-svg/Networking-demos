Two branches: LA and NY  
LA branch: vlan 10 - 40 (HR IT Sales Servers)  
NY branch: vlan 50 - 70 (HR IT Sales)  
each have svis configured / ex: 192.168.10.1 = vlan 10 , 192.168.20.1 = vlan 20  
branch office routers are dhcp servers  
a pool for each vlan is configured, 192.168.40.10 is dns server  
ospf is configured on l3 switch and routers  
link type is p2p  
nat configured on head office router, translates 192.168.x.x traffic using pat  
to do:  
implement acls?  
