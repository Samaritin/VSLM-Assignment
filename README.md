# VSLM Assignment

**Overview:** This lab focused on designing a network using Variable Length Subnet Masking (VLSM) to optimize IP address allocation across departments.

**Skills Developed:** Subnetting using VLSM, IP address allocation, network design.

**Tools Used:** VLSM Calculators, ipconfig, ping.

---

**Lab Details**

To find the IP Scheme for a company with an IP address of 192.168.1.0/24 that has four different departments making up Sales, Dev, Accounts, and Management each having their own set number of computers. Without going into the bits portion of it, the individual would need to allocate the network into how many hosts each department needs. The sales department is made up of 120, the Dev department is made up of 50, the Accounts department is made up of 26, and the Management department is made up of 5 computers. This is important because when subnetting and assigning IP addresses to each department it is based on the size requirements needed. 
The individual will need to determine the number of subnets needed for each department and allow enough room in the network for the company to grow. If the individual does not do this, they will have to continually keep adjusting the subnet size and this may cost the company money. The Sales and Dev department will require 2 subnets, one for users and one for servers. While the Accounts and Management department will require 1 subnet. 
The Sales department requires 120 host addresses for the users and 30 host addresses for the servers. The Dev department requires 50 host addresses for the users and 10 host addresses for the servers. The Accounts department requires 26 host addresses, and the Management department requires 5 host addresses. 
Now the individual has the number of hosts for each department and can start assigning the subnetting mask for each host. To begin, since the network address is 192.168.1.0 /24, and the subnet mask is 255.255.255.0. An individual can use the CIDR (Classless Inter-Domain Routing or supernetting) to help with subnetting as well. Once the number of bits reaches /24 in CIDR notation or 255.255.0.0. then it must borrow the correct number of bits until it reaches the correct number of hosts needed for the necessary subnet. In the Sales department, it only needs to borrow 1 bit to reach 128 host for a /25 CIDR notation for a subnet mask of 255.255.255.128 for the users and 255.255.255.224 /27 for the servers for extra space. Continuing, the Dev department’s subnet would be 255.255.255.192 /26 for the users and 255.255.255.240 /28 for the servers for space. Then the Accounts department would be 255.255.255.192 /26 and the Management department would be 255.255.255.248 /29. These will help us determine the Variable Length Subnet Mask for the company. 

The IP addresses assigned for each department are as follows. For the Sales department: 192.168.1.0/25 for users and 192.168.1.128/27 for servers. The Dev department: 192.168.1.160/26 for users and 192.168.1.192/28 for servers. The Accounts department: 192.168.1.224/26. The Management department: 192.168.1.232/29. This is created keeping the Class C IP main network address and subtracting 2 from the network mask host as well. Therefore, the IP Range for the departments will be for Sales subnet 192.168.1.1-192.168.1.126, for Dev subnet 192.168.1.129-192.168.1.190, for Accounts 192.168.1.193 – 192.168.1.222, and for Management the subnet will be 192.168.1.225 – 192.168.1.230. This scheme provides the smallest subnet without wasting further IP addresses with allowing some reserved for network and broadcast within the network as well.  



An easier view of the information is Below: 
Sales Department: 120 host 	255.255.255.128	192.168.1.1 – 192.168.1.126
Dev Department: 50 host 	255.255.255.192	192.168.1.129 – 192.168.1.190
Accounts Department: 26 	255.255.255.244	192.168.1.193 – 192.168.1.222
Management Department: 5 	255.255.255.248	192.168.1.225 – 192.168.1.230	

![image](https://github.com/user-attachments/assets/8ab67c34-8b20-4c4b-87ae-32500272865e)

