# Overview
This lab simulates a small multi-site enterprise network with two branch offices connected to a central headquarters router. Each branch contains several departmental VLANs, and traffic between sites is dynamically routed using OSPF. Internet access is provided through the headquarters router using NAT overload (PAT), allowing internal private networks to reach external resources.

The goal of this lab was to combine several networking concepts into a single environment that more closely resembles a real enterprise deployment rather than isolated configuration exercises.

## Network Topology
The topology consists of:
* Two Branch Sites (LA & NY)
* Layer 3 switch at each branch for inter-VLAN routing
* A central HQ router that connects the branches
* A simulated ISP router to represent the internet  

Each branch site connects to the HQ router through point-to-point WAN links using /30 networks. OSPF is used to dynamically exchange routes between the routers so that each site can reach the internal networks of the other.

Internet connectivity is simulated by connecting the HQ router to an external router which hosts a public test address.

## VLAN segementation
Branch 1:
* VLAN 10 - HR
* VLAN 20 - IT
* VLAN 30 - Sales
* VLAN 40 - Servers

Branch 2:
* VLAN 50 - HR
* VLAN 60 - IT
* VLAN 70 - Sales

Each branch office contains multiple VLANs to represent separate departments within the organization. Segmenting departments into separate VLANs helps isolate broadcast domains and reflects how organizations typically separate network traffic between teams. 

## Inter-VLAN Routing
Inter-VLAN routing is handled by the Layer 3 switches at each branch. SVIs were created for each VLAN to act as the default gateway for hosts within that network. This allows devices in different departments to communicate while maintaining logical separation between networks.

## Dynamic Routing with OSPF
OSPF was implemented between the branch routers and the HQ router to automatically exchange routing information.

Each WAN link was configured as a point-to-point network, and the routers advertise their connected networks into OSPF. This allows both branch locations to learn routes to each other without relying on static routing.

Using OSPF also makes the network easier to scale. Additional branch offices could be added with minimal changes to the existing routing configuration.

## Internet access with NAT
The HQ router acts as the network edge and performs NAT overload (PAT) to allow internal clients to reach external networks.

Private address ranges from the branch VLANs are translated to the public address assigned to the HQ router's Internet interface.

This allows hosts from either branch to reach the simulated external network while keeping internal IP addressing private.











