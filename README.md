## Ex. No: 4  VLAN Configuration Using a Managed Switch
## Date: 30/07/2026
## Name: KISHORE J
## Reg No: 212223060127
________________________________________
# Objective
To configure Virtual Local Area Networks (VLANs) on a managed switch and verify that hosts within the same VLAN can communicate while others cannot.
________________________________________
# Apparatus/Tools Required
•	Cisco Packet Tracer<br>
•	1 Managed Switch (e.g., 2960)<br>
•	4 PCs<br>
•	Straight-through Ethernet cables<br>
________________________________________
# Network Topology Diagram
Description:<br>
•	PC0 and PC1 are assigned to VLAN 10.<br>
•	PC2 and PC3 are assigned to VLAN 20.<br>
•	All PCs are connected to different ports on the same switch.<br>
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/32f3a886-4198-4ec1-83a1-f77a44c14614" />

________________________________________
# IP Addressing Table
Device	VLAN	IP Address	Subnet Mask	Port<br>
PC0	10	192.168.10.1	255.255.255.0	FastEthernet0/1<br>
PC1	10	192.168.10.2	255.255.255.0	FastEthernet0/2<br>
PC2	20	192.168.20.1	255.255.255.0	FastEthernet0/3<br>
PC3	20	192.168.20.2	255.255.255.0	FastEthernet0/4<br>
________________________________________
# Procedure
1.	Open Cisco Packet Tracer and add 4 PCs and 1 Switch.<br>
2.	Connect PC0–PC3 to switch ports FastEthernet0/1 to FastEthernet0/4 respectively.<br>
3.	Assign static IP addresses to each PC as per the IP table.<br>
4.	Enter the Switch CLI and create two VLANs:<br>
o	VLAN 10 for PC0 and PC1<br>
o	VLAN 20 for PC2 and PC3<br>
5.	Assign the respective switch ports to their VLANs.<br>
6.	Use the ping command from PC0 to PC1 (should succeed).<br>
7.	Try pinging from PC0 to PC2 (should fail — different VLANs).<br>
________________________________________
# Commands Used (Switch CLI)
bash<br>
CopyEdit<br>
Switch> enable<br>
Switch# configure terminal<br>

Switch(config)# vlan 10<br>
Switch(config-vlan)# name STAFF<br>
Switch(config-vlan)# exit<br>

Switch(config)# vlan 20<br>
Switch(config-vlan)# name STUDENTS<br>
Switch(config-vlan)# exit<br>

Switch(config)# interface range fastethernet0/1 - 2<br>
Switch(config-if-range)# switchport mode access<br>
Switch(config-if-range)# switchport access vlan 10<br>
Switch(config-if-range)# exit<br>

Switch(config)# interface range fastethernet0/3 - 4<br>
Switch(config-if-range)# switchport mode access<br>
Switch(config-if-range)# switchport access vlan 20<br>
Switch(config-if-range)# exit<br>
________________________________________
# Output (Screenshots)
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f90f52c3-150b-4414-8fbd-d18060b5fd66" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9facabd4-c90d-488e-97f7-1320fe3d98ee" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/215e894b-3ea9-4691-9fa9-721828182039" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/696dd5b5-a4dd-458e-a06e-43736c02bfa6" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/137c233f-6318-4a99-b8d9-ae64755dfca2" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e692e906-ed75-4ae2-b744-3e72fe74776f" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/88b5d163-f2ef-4dc2-ad1e-ff812351c18e" />

•	VLAN configuration on switch<br>
•	PC IP settings<br>
•	Successful ping between PCs in the same VLAN<br>
•	Failed ping between PCs in different VLANs<br>
________________________________________
# Result
Successfully created and configured VLANs on a managed switch. Verified that only PCs within the same VLAN could communicate with each other.

