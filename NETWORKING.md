Azure networks :

Like how we have Multiple phone numbers to contact each other as like that n/w has something called IP Address 
And we have 

IP V4
IP V6
IP V4 

Is usually 8 bit .8bit. 8bit.8bit = 32 bit IP addressing

Here we I can do sub netting and super netting to classify into multiple small pieces of n/w
We have 5 different classes of IP address :
1. A 0-126
2. B 128-191
3. C 192-223
4. D 224-239
5. E 240-255
127 is called loopback IP address

Then IP address are start from 0.0.0.0 , 0.0.0.1,...…........
...to......,255.255.255.255

Then if network is big the we can use 10.1.0.0/16 means that first two blocks are blocked and we can create subnets are 
10.1.1.0/24 means that there is a chance to create 255 subnets

Classifications of IP address :

Public IP

It is mainly for management traffic


Private IP:

If two virtual machines communicating each other then it is always via private IP

We have reserved private IP

1. 10.0.0.0 - 10.255.255.255
2. 172.16.0.0 - 172.31.255.255
3. 198.168.0.0 - 192.168.255.255


Create a new boundary logical boundary which is my recourse group which called N/W boundary
 in the network boundary Iam creating a Vnet with IP Address of 10.1.0.0/16
Everybody in the vnet will communicate each other 
To give some security in my virtual network Iam going to create subnets 
 then my subnets named as s1 and s2 
I will assign ip to s1 is 10.1.1.0/24(within this I can create 256 subnets)
I will assign ip to s1 is 10.1.2.0/24

Azure reserved some IP are 0,1,2,3 and 255
0 is for network 
1,2,3 is for azure for future 
255 is for broadcast IP

Any machine you created that needs a ip address will picked up from subnet address
In this sub net you want to create machines 
Machines will have network interface card NIC
Virtual networks

 networking Page 1 
Machines will have network interface card NIC

Create IP addresses :
 Public IP:
These are accessible for publics from the internet
Private IP:
Which can be only accessible within in a network you cant connect from outside
These Ips can be dynamic and static
Dynamic:
Evrytime the dynamic ip can change (when you assign a dynamic when machines start the ip will change)
Static Ip :
It always remain same (when you start a machine the static ip can be remains same)
IP V6 
It usually has 128 bit alpha numeric IP addressing

