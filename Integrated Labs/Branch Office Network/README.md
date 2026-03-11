# Overview
This lab simulates a small multi-site enterprise network with two branch offices connected to a central headquarters router. Each branch contains several departmental VLANs, and traffic between sites is dynamically routed using OSPF. Internet access is provided through the headquarters router using NAT overload (PAT), allowing internal private networks to reach external resources.

The goal of this lab was to combine several networking concepts into a single environment that more closely resembles a real enterprise deployment rather than isolated configuration exercises.

## Network Topology
![Topology](images/topology&internet/network%20topology.png)  
The topology consists of:
* Two Branch Sites (LA & NY)
* Layer 3 switch at each branch for inter-VLAN routing
* A central HQ router that connects the branches
* A simulated ISP router to represent the internet  

Each branch site connects to the HQ router through point-to-point WAN links using /30 networks. OSPF is used to dynamically exchange routes between the routers so that each site can reach the internal networks of the other.

Internet connectivity is simulated by connecting the HQ router to an external router which hosts a public test address.

## VLAN segementation
Branch 1 (LA):
* VLAN 10 - HR
* VLAN 20 - IT
* VLAN 30 - Sales
* VLAN 40 - Servers

Branch 2 (NY):
* VLAN 50 - HR
* VLAN 60 - IT
* VLAN 70 - Sales

![LA-VLAN](images/la/la%20vlans.png)
![NY-VLAN](images/ny/ny%20vlans.png)  

## Inter-VLAN Routing
Inter-VLAN routing is handled by the Layer 3 switches at each branch. SVIs were created for each VLAN to act as the default gateway for hosts within that network. This allows devices in different departments to communicate while maintaining logical separation between networks.

![LA-SVI](images/la/la%20l3%20switch%20ip%20configs.png)  
![NY-SVI](images/ny/ny%20l3%20switch%20ip%20configs.png)  

## Dynamic Routing with OSPF
OSPF was implemented between the branch routers and the HQ router to automatically exchange routing information.

Each WAN link was configured as a point-to-point network, and the routers advertise their connected networks into OSPF. This allows both branch locations to learn routes to each other without relying on static routing.

Using OSPF also makes the network easier to scale. Additional branch offices could be added with minimal changes to the existing routing configuration.  
* LA L3 Switch & LA Router OSPF neighbors  
![LA-OSPF](images/la/la%20l3%20sw%20ospf.png)
![LA-OSPF](images/la/la%20router%20ospf.png)

* NY L3 Switch & NY Router OSPF neighbors  
![NY-OSPF](images/ny/ny%20l3%20sw%20ospf.png)
![NY-OSPF](images/ny/ny%20router%20ospf.png)

* HQ Router OSPF neighbors with LA & NY Routers  
![HQ-OSPF](images/hq/hq%20router%20ospf%20config.png)

## Internet access with NAT
The HQ router acts as the network edge and performs NAT overload (PAT) to allow internal clients to reach external networks.

Private address ranges from the branch VLANs are translated to the public address assigned to the HQ router's Internet interface.

![NAT](images/validation/nat%20translation%20of%20la%20branch%20sales%20user%20inside%20to%20outside%20ip.png)  

This allows hosts from either branch to reach the simulated external network while keeping internal IP addressing private.

## Validation
Connectivity was verified through several tests:
* Hosts within the same VLAN can successfully communicate with each other (HR VLAN ip addressing: 192.168.10.x for LA branch & 192.168.50.x for NY branch) 

* Inter-VLAN communication works through the Layer 3 switches

![inter-vlan](images/validation/vlan%20&%20%20inter-vlan%20communication.png) 
  
* Branch networks can reach each other through OSPF (tracert demonstrates the packet traveling between OSPF learned routes) 

![LA-ROUTES](images/la/la%20router%20ip%20routes.png)  
![NY-ROUTES](images/ny/ny%20router%20ip%20routes.png)  
![reaching-via-ospf](images/validation/reaching%20la%20branch%20as%20user%20IT2%20in%20ny%20branch.png)  
  
* Internal hosts can reach the simulated Internet address (8.8.8.8) through NAT

![internet-config](images/topology&internet/internet%20ip%20config.png)  
![natting](images/validation/pinging%20internet%20as%20la%20branch%20sales%20user.png)  

## Network Design Decisions
A few design choices were made while building the lab to keep the topology both realistic and scalable.

Unique subnets per site:
* Each branch uses different subnet ranges rather than reusing the same VLAN networks across locations. While departments are similar across branches, using unique addressing prevents overlapping networks and allows routers to properly distinguish traffic between sites.

Layer 3 switching at the branch:
* Inter-VLAN routing is performed by Layer 3 switches at each branch instead of the routers. This keeps local traffic within the branch and prevents unnecessary routing across the WAN. It also reflects how many enterprise networks operate, where distribution or access layer switches handle local routing for internal VLANs.

Dynamic routing with OSPF:
* OSPF was chosen instead of static routing to allow the network to scale more easily. If additional branch sites were added in the future, they could join the routing domain and advertise their networks without requiring manual route configuration on every router.

Centralized NAT at HQ:
* Instead of performing NAT at each branch, NAT is handled at the HQ router. This mirrors how many organizations design their networks, where branches use private addressing internally and internet access is routed through a central edge device. Centralizing NAT also simplifies management and allows all outbound traffic to be monitored or filtered at a single point.

Layer 3 switching at the branch:
* Inter-VLAN routing is performed by Layer 3 switches at each branch instead of the routers. This keeps local traffic within the branch and prevents unnecessary routing across the WAN. It also reflects how many enterprise networks operate, where distribution or access layer switches handle local routing for internal VLANs.

## Troubleshooting challenges encountered
While building the topology, several issues came up that required troubleshooting.

DHCP clients receiving APIPA addresses:
* Initially hosts were receiving 169.254.x.x addresses. This was caused by missing routing between the branch router and the Layer 3 switch where the VLAN interfaces were configured. Once the proper routes were added, DHCP requests were successfully forwarded from the router to the SVIs and ultimately the endhosts requesting the IP address.

OSPF adjacency dropping:
* After configuring NAT on the HQ router, the OSPF neighbor relationship between routers dropped and the dead timer eventually expired. This was caused by accidentally applying the ACL used for NAT directly to the interface with an access-group. Since the ACL only permitted internal LAN traffic, it blocked OSPF hello packets (protocol 89) from passing across the link. Once the ACL was removed from the interface and left only for NAT matching, OSPF adjacencies formed normally again.

These troubleshooting steps helped reinforce the importance of validating routing, interface roles, and control-plane protocols when making changes to an existing network.

## Key Takeaways
This lab helped reinforce several important networking concepts:
* Designing a multi-site network with unique subnet addressing
* Implementing VLAN segmentation for departmental isolation
* Using OSPF for dynamic route exchange between sites
* Configuring NAT overload to provide internet access for private networks
* Understanding how routing and NAT interact at the network edge

Combining these features into a single topology provided a more in-depth and realistic look at how enterprise networks are structured and managed.
