# Fully Redundant Company LAN Network
![Diagram ](https://github.com/Tjeewantha/Company-Network-Project_Redundancy_CCNA/blob/main/Company%20Network_Diagram.jpg "Diagram ")

The company has built up with three floors. The server room and IT department is located in ground floor while the first floor and second floor contribute for the team of Sales, Marketing, HR, Logistic and Finance, Accounting, Administration, Public-Relation respectively. Every couple of departments belong to separate VLAN and each department have** at least 200 **users. Also, certain users in all department have IP telephony systems.

Breaking down VLAN separation
- VLAN 10 - Sales and Marketing Department
- VLAN 20 - HR and Logistic Department
- VLAN 30 - Finance and Account Department
- VLAN 40 - Administrator and Public Relation Department
- VLAN 50 - ICT
- VLAN 60 – Servers
- VLAN 200-Voice 

The company has two ISPs that connects with LAN by providing full redundancy for the network. OPSF (single area) protocol uses to route Ip packets between L3 Switches and Routers. As users need to access Internet, the dynamic NAT (Overload) configured on Routers interfaces. To enable routing between VLANs and increase links bandwidth, SVI interfaces configured on all L3 Switches and VTP is used to share VLAN information between L2 Switches.

The SYSTEM_SERVER and INTERNAL_SERVER resides in Server-Room. While the SYSTEM_SERVER provides services such as Webhosting and DNS, the INTERNAL_SERVER provides services such as NTP, DHCP, FTP, etc.  All users get their IP address from DHCP server and all users can log into system server through the URL “**system.company.com**”. the NTP server is used to synchronize time in all intermediary devices.  

Moreover, each VLAN has separate wireless network so that every department connects with wireless access points. Wireless LAN Controller which has been connected to L2 Switch in Server-Room, is used to centrally manage all the Aps. To make it work, **Management VLAN (200)** set up as native VLAN on every trunk link. 

IP Configuration (VLAN-HSRP)

| VLAN Number  |Network|  Interface address |  Virtual IP |
| ------------ | ------------ | ------------ | ------------ |
| VLAN 10  |  172.16.10.0/24 |172.16.10.1\172.16.10.2 |  172.16.10.3 |
| VLAN 20  | 172.16.20.0/24  |172.16.20.1\72.16.20.2|  172.16.20.3 |
|  VLAN 30 |  172.16.30.0/24 |172.16.30.1\172.16.30.2|  172.16.30.3 |
| VLAN 40  |172.16.40.0/24|172.16.40.1\172.16.40.2| 172.16.40.3  |
|VLAN 50|  172.16.50.0/24  |172.16.50.1\172.16.50.2| 172.16.50.3  |
|  VLAN 60 | 172.16.60.0/24  | 172.16.60.1\72.16.60.2|  172.16.60.3 |
|  VLAN 100 |172.16.100.0/24   | 172.16.100.1\72.16.100.2|  172.16.100.3 |



