# Small Office Network Design – Cisco Packet Tracer

## 📌 Project Overview
This project presents the design and implementation of a small office Local Area 
Network (LAN) for a startup company using Cisco Packet Tracer. The network 
connects four departments — Management (2 PCs), Accounts (3 PCs), Sales (4 PCs), 
and IT Support (2 PCs) — totaling 11 computers, using a star topology with a 
central switch and router.

## 🎯 Objectives
- Analyze the networking requirements of a small office environment
- Design an efficient, cost-effective star topology LAN
- Select appropriate networking devices, transmission media, and an IP addressing scheme
- Implement and configure the network in Cisco Packet Tracer
- Verify end-to-end connectivity using ping tests
- Evaluate performance, collision handling, and scalability
- Compare the design against a VLAN-based alternative

## 🖥️ Network Topology
Star topology — all 11 PCs connect to a central switch, which connects to a router 
acting as the default gateway.

| Department  | PCs |
|-------------|-----|
| Management  | 2   |
| Accounts    | 3   |
| Sales       | 4   |
| IT Support  | 2   |
| **Total**   | **11** |

## 🛠️ Devices Used
| Device                       | Role                          |
|------------------------------|--------------------------------|
| Cisco 2911 Router             | Default gateway                |
| Cisco Catalyst 2960 Switch    | Central Layer 2 switching device |
| 11 × PC                       | Department workstations        |
| Copper Straight-Through cables| Router–Switch and Switch–PC links |

## 🌐 IP Addressing Scheme
- **Network:** 192.168.10.0/24
- **Subnet Mask:** 255.255.255.0
- **Default Gateway (Router):** 192.168.10.1
- **Switch Management IP:** 192.168.10.2
- **DNS Server:** 8.8.8.8
- **PC IPs:** Static, assigned uniquely within 192.168.10.0/24

## ⚙️ Implementation Steps
1. Designed the network topology in Cisco Packet Tracer using a star topology.
2. Added one Cisco 2911 router, one Cisco Catalyst 2960 switch, and eleven PCs.
3. Connected the router to the switch and all PCs to the switch using Copper 
   Straight-Through Ethernet cables.
4. Configured the router interface (GigabitEthernet0/0) with IP 192.168.10.1/24.
5. Assigned management IP 192.168.10.2/24 to the switch.
6. Configured static IPv4 addresses on all 11 end-user PCs.
7. Verified end-to-end connectivity using the `ping` command.
8. Saved router and switch configurations for persistence after reboot.

## ✅ Testing & Results
Connectivity was verified using ping tests between all PCs and the router. 
All tests returned **0% packet loss**, confirming correct configuration and 
reliable communication across the network.

## 📊 Performance & Collision Analysis
- The Catalyst 2960 switch creates a separate collision domain per port, 
  eliminating unnecessary collisions (unlike a hub).
- Full-duplex communication further removes collisions during simultaneous 
  send/receive operations.
- Data frames are forwarded only to their intended destination via the switch's 
  MAC address table, reducing unnecessary traffic.

## 📈 Scalability
The Catalyst 2960 switch has unused ports available for future device additions, 
and the 192.168.10.0/24 addressing scheme has sufficient address space to support 
organizational growth without redesigning the network.

## 🔀 Alternative Design Considered
A VLAN-based design (one VLAN per department with router-on-a-stick inter-VLAN 
routing) was evaluated as an alternative. While it would improve security and 
reduce broadcast traffic, it was not implemented due to the added configuration 
complexity and cost, which weren't justified for the startup's current size and budget.

## 🚀 Future Improvements
- Implement VLANs to segment departmental traffic and improve security
- Deploy a DHCP server for automated IP address assignment
- Add a firewall for perimeter security
- Add a wireless access point for laptop/smartphone connectivity
- Introduce a file server and network printer for centralized resource sharing

## 📂 Repository Contents
- `network-topology.pkt` – Cisco Packet Tracer project file
- `screenshots/` – Topology, router/switch/PC configuration, and ping test results
- `README.md` – Project documentation

## 🧰 Tools Used
- Cisco Packet Tracer

## 👤 Author
Naeem Khan  
Registration No.: 24PWCSE2379  
Department of Computer Systems Engineering, University of Engineering and Technology, Peshawar
