LAB 1 introduction 

In this lab , we will need to setup a internetwork to fulfill below requirement. 


a. 1 p2p circuit connect between office and warehouse
b. small office with limit budget
c. Seprate 2 vlans, 1 for office staff , 1 for IT equipement 
d. office worker will need to connect the server & database in the server room.


solution 

Site 1 Office 

 - Router (R1) 

interface SE0/1 connecting to ISP router (BELL)
subnet : 192.168.200.0/30 
se0/1 : 192.168.200.1

interface SE0/0 connecting to site2 warehouse (p2p)
subnet : 192.168.0.0/30
se0/0 192.168.0.2

interface fa0/0 connecting to switch 1 (ROAS)
vlan 10 (IT) 192.168.10.0/29
vlan 20 (staff) 192.168.20.0/29

DHCP server for vlan20 192.168.20.0/29
DNS : 8.8.8.8

 - Switchs (S1-3) 

RSTP 
S2 as the root for vlan 2
s3 as the root for vlan 3
enable portfast and bpduguard 
shutdown unused ports 

Site2 warehosue 

 - Router (R2)

 interface se0/1 connecting to isp router (telus)
 subnet : 192.168.100.0/30
 se0/1 : 192.168.100.1

 interface se0/0 connecting to office 
 subnet : 192.168.0.0/30
 se0/0 : 192.168.0.1

 interface fa0/0 connecting to switch S4
 DHCP server for vlan 30 192.68.30.0/29
 DNS : 8.8.8.8

 - Switch (S4) 
 shutdown unused ports 
