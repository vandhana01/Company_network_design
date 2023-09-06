# Company_Network_Design



<img width="918" alt="image" src="https://github.com/vandhana01/Company_network_design/assets/142392052/d43b4e23-426f-4d6b-8fd1-8c2291f2e63f">

## Problem Statement
+ A trading floor support center employs 600 staff. They have recently expanded and as a result, need to move to a new building. A building has been identified but has no network. This means that before they can make to move out, new network service needs to be designed and implemented in the new building. Existing network comprises of the following:

+ The new building is expected to have three floors with two departments in each floor:

1.	First floor (Sales and Marketing Department – 120 users expected, Human Resources and Logistics Department – 120 users expected)
2.	Second floor (Finance and Accounts Department – 120 users expected, Administrator and Public Relations Department – 120 users expected)
3.	Third floor (ICT – 120 users expected, Server Room – 120 users expected)

+ Therefore, as a key member of the Networks team, we have been tasked to design a network for the new building. Hence, to design the proposed Company network design, we have used Cisco Packet Tracer simulator software.

# Introduction
Network management refers to two related concepts. First is the process of configuring, monitoring, and managing the performance of a network. Second is the platform that IT and  NetOps  teams use to complete these ongoing tasks.

LAN stands for Local Area Network is a group of network devices which allow the communication between connected devices. On the other hand VLAN stands for Virtual Local Area Network which is used to enhance the performance of LANs. Virtual local area networks have become crucial for organizations with complex networking systems. Organizations require solutions that allow them to scale their networks, segment them to increase security measures, and decrease network latency.

The main difference between LAN (Local Area Network) and VLAN (Virtual Local Area Network) is that LAN work on a single broadcast domain on the other hand VLAN works on multiple broadcast domain and In a local area network, the Packet is advertised to each device while In virtual local area network, the packet is sent to a specific broadcast domain. 

## Advantages of VLAN
+	VLAN broadcasting reduces the size of the broadcast domain.
+	VLAN device provides more security.
+	Device management through VLAN is simple and easy.
+ It is easy and fast to add, remove or make changes
+ The network devices in the network as an extra layer of security.

# Methodology
 In order to design Company network, the following are the requirements:
1.	Use Cisco Packet Tracer to design and implement the network solution.
2.	Use hierarchical model providing redundancy at every layer, that is, two routers and two multilayer switches are expected to be used to provide redundancy.
3.	The network is also expected to connect to at least two ISPs to provide redundancy and each router to be connected to the two ISPs.
4.	Each department is required to have a wireless network for the users.
5.	Each department should be in a different VLAN and in different subnetwork.
6.	Provided a base network of 172.16.1.0, carry out sub-netting to allocate the correct number of IP addresses to each department.
7.	The company network is connected to the static, public IP addresses 195.136.17.0/30, 192.136.17.4/30, 195.136.17.8/30 and 195.136.17.12/30 connected to the two Internet providers.
8.	Configure basic device settings such as hostnames, console password, enable password, banner messages, disable  IP domain lookup.
9.	Devices in all the departments are required to communicate with each other with the respective multilayer switch configured for inter-VLAN routing.
10.	The multilayer switches are expected to carry out both routing and switching functionalities thus will be assigned IP addresses.
11.	All the devices in the network are expected to obtain an IP address dynamically from the dedicated DHCP servers located at the server room.
12.	Devices in the server room are to be allocated IP address statically.
13.	Use OSPF as the routing protocol to advertise routes, both on the routers and multilayer switches.
14.	Configure SSH in all the routers and layer three switches for remote login.
15.	Configure port-security for the Finance and Accounts department to allow only one device to connect to a switch port, use sticky method to obtain mac-address and violation mode shutdown.
16.	Configure PAT to use the respective outbound router interface IPv4 address, implement the necessary ACL rule.
17.	Test Communication, ensure everything configured is working as expected.

# Implementation
The steps involved in the implementation are:

1.	Basic settings to all the devices plus SSH on the routers and 13 switches.
2.	VLANs assignment plus all access and trunk ports on 12 and 13 switches.
3.	Switch port security to finance department.
4.	Subnetting and IP addressing.
      ###  Provided base network of 172.16.1.0

### First Floor 
 
| Department | Network Address | Subnet Mask | Host Address Range | Broadcast Address |
| ---------- | --------------- | ----------- | ------------------ | ----------------- |
| Sales and MArketing | 172.16.1.0 | 255.255.255.128/25 | 172.16.1.1 to 172.16.1.126 | 172.16.1.127 |
| HR and Logistics | 172.16.1.128 | 255.255.255.128/25 | 172.16.1.129 to 172.16.1.254 | 172.16.1.255 |

### Second Floor

| Department | Network Address | Subnet Mask | Host Address Range | Broadcast Address |
| ---------- | --------------- | ----------- | ------------------ | ----------------- |
| Finance and Accounts | 172.16.2.0 | 255.255.255.128/25 | 172.16.2.1 to 172.16.2.126 | 172.16.2.127 |
| Admin & Public relation | 172.16.2.128 | 255.255.255.128/25 | 172.16.2.129 to 172.16.2.254 | 172.16.2.255 |

### Third Floor

| Department | Network Address | Subnet Mask | Host Address Range | Broadcast Address |
| ---------- | --------------- | ----------- | ------------------ | ----------------- |
| ICT | 172.16.3.0 | 255.255.255.128/25 | 172.16.3.1 to 172.16.3.126 | 172.16.3.127 |
| Server Room | 172.16.3.128 | 255.255.255.240/25 | 172.16.3.129 to 172.16.3.142 | 172.16.3.143 |

### Between the Routers and Layer-3 Switches 

| No.	| Network Address	| Subnet Mask	| Host Address Range | Broadcast Address |
| --- | --------------- | ----------- | ------------------ | ----------------- |
| R1-MLSW1 | 172.16.3.144	| 255.255.255.252 |	172.16.3.145 to 172.16.3.146 | 172.16.3.147 |
| R1-MLSW2 | 172.16.3.148 |	255.255.255.252 |	172.16.3.149 to 172.16.3.150 | 172.16.3.151 |
| R1-MLSW3 | 172.16.3.152 |	255.255.255.252 | 172.16.3.153 to 172.16.3.154 | 172.16.3.155 |
| R1-MLSW4 | 172.16.3.156 | 255.255.255.252 |	172.16.3.157 to 172.16.3.158 | 172.16.3.159 |

### Between the Routers and Layer-3 Switches

Public IP addresses 195.136.17.0/30, 192.136.17.4/30, 195.136.17.8/30 and 195.136.17.12/30.

5.	OSPF on the routers and 13 switches.
6.	Static IP address to server room devices.
7.	DHCP server device configurations.
8.	Inter-vLAN routing on the 13 switches plus IP DHCP helper addresses.
9.	Wireless network configurations.
10.	 PAT + Access control list.
11.	Verifying and testing configurations.
 
# Results
![image](https://github.com/vandhana01/Company_network_design/assets/142392052/0b4095af-2fad-4545-bb36-38964b1ac31c)

![image](https://github.com/vandhana01/Company_network_design/assets/142392052/27bbd90e-3977-4270-b5bd-4ef88aeb5679)

![image](https://github.com/vandhana01/Company_network_design/assets/142392052/501d2736-ac2e-45a5-99b4-f9a99602d2ab)



# Conclusion
- We can conclude that the load and traffic of switches are reduced by creating VLAN. We are able to ping two different PCs from two different floors of different departments. We could send and receive data from host to every other servers. 
- The software application of cisco packet tracer can be used to design and analyze the simulation data and the traffic in computer networks and can be utilized as an information about the state of the computer connection in the network so that it can be used to detect damage to the computer network in a fast, easy, and inexpensive.
