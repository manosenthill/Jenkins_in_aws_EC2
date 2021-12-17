Creating VPC,Subnets,Internet Gateway and NAT gateway
##Creating VPC
VPC-A virtual private cloud (VPC) is a virtual network dedicated to your AWS account. It is logically isolated from other virtual networks in the AWS Cloud.
To create our own vpc
Go to the amazon console
In the search services box  type VPC
      VPC HOME IMAAGE
      Click Your VPC
      Click Create VPC
      CREATE VPC IMG
      
      #### CIDR
      Classless Inter-Domain Routing (CIDR) blocks are for specifying a range to IP addresses in format of IPv4 or IPv6.
      General format for CIDR Blocks: x.y.z.t/p
      x, y, z and t are numbers from 0 to 255. Basically, each represents an 8 bit binary number. That's why it is range is up to 255. Combination of this numbers becomes an IPv4 IP address that must be unique to be able to identify a specific instance.
      In case of AWS, p is a number from 16 to 28. It represents the number of bits that are inherited from given IP address.
      For example: 10.0.0.0/16 represents an IP address in following format: 10.0.x.y where x and y are any number from 0 to 255. 
      So, actually it represents a range of IP addresses, starting from 10.0.0.0 to 10.0.255.255.

      However for each CIDR block, AWS prohibits 5 possible IP addresses. Those are the first 4 available addresses and the last available address. In this case:

10.0.0.0: Network address
10.0.0.1: Reserved for VPC router
10.0.0.2: DNS server
10.0.0.3: Reserved for future use
10.0.255.255: Network broadcast  
When you create a VPC, you must specify a range of IPv4 addresses for the VPC in the form of a Classless Inter-Domain Routing (CIDR) block.
How to calculate CIDR 
suppose the IPV4 CIDR is 10.0.0.0/26
2^(32-26)=2^6=64 
so we have 64 avilable ip addresses.
It starts with 10.0.0.0
Ends with  10.0.0.63
## Creating Subnets
Sunbnets are Range of IP Addresses.Currently wecan create 200 subnets per VPC. If you would like to create more, we have to submit a case at the support center.
subnets can't span across availability zones.
Here we are going to create two private and two public subnets in the ip range of 10.0.0.0/26
we are going to divide the cidr to 4 equal block for each subnets.so each subnets can have 16 ip address.
On the VPC Dashboard
click subnets
img private-a
In the create subnet wizard choose your VPC
Name the subnet and choose the avilability zone.
Give the IP range for the first subnet
10.0.0.0/28
2^(32-28)
2^(4)=16 IP address for our FIRST PrIVATE SUBNET.




create route tables
associate subnets to the route table
create internet gateway
Cteate NAT
