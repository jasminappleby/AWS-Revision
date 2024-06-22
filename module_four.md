# Connectivity to AWS

- Imagine the millions of customers using AWS services, and imagine the millions of resources these customers have created, such as EC2 instances. 
- Without boundaries around all of these resources, network traffic would be able to flow between them unrestricted.

## Amazon Virtual Private Cloud (Amazon VPC)
- A network service that you can use to establish boundaries around your AWS resources. 
- Enables you to provision an isolated section of the AWS Cloud.
- In this isolated section, you can launch resources in a virtual network that you define.
- Within a VPC, you can organise your resources into subnets. A subnet is a section of a VPC that can contain resources such as Amazon EC2 instances.

## Internet Gateway
- To allow public traffic from the internet to access your VPC, you attach an internet gateway to the VPC.
- A connection between VPC and the internet. Similar to a doorway that customers would use to enter a store.
- Without an Internet Gateway, no one can access the resources within your VPC.

## Virtual Private Gateway
- VPC includes only private resources.
- Extra layer of protection, imagine if you were walking down the street with regular people but you had a bodyguard.
- The bodyguard is equivelant to the VPN connection that encrypts your internet traffic from all other requests around it. 
- VPG is the component that allows protected internet traffic to enter into the VPC. 
- Even though your connection to the coffee shop has extra protection, traffic jams are possible because you are still using the same road as other customers.

A virtual private gateway enables you to establish a virtual private network connection between your VPC and a private network. An example would be an on-premise data center or internal corporate network. A virtual private gateway allows traffic into the VPC only if it is coming from an approved network. 

## AWS Direct Connect
AWS Direct Service is a service that enables you to establish a dedicated private connection between your data centre and a VPC. 

If there was an apartment building with a hallway directly linking the building to the coffee shop. Only the residents of the apartment building can travel through this hallway. 

The private hallway provides the same type of dedicated connection as AWS Direct Connect. Residents are able to get into the coffee shop without needing to use the public road shared with other customers.

The private connection that AWS Direct Connect provides helps you to reduce network costs and increase the amount of bandwidth that can travel through your network. 


Security Group is _stateful_ and this means it will remember the traffic when it comes in and can allow it to leave.

Network ACL is _stateless_ and this means that it will need to check traffic when it enters and when it leaves. 

# Connectivity to AWS

## Connectivity to AWS Amazon Virtual Private Cloud (Amazon VPC)
There are millions of customers who use AWS services and resources. These customers have also created millions of resources like EC2 instances. Without boundaries around these resources, the network traffic would be able to flow between them unrestricted. 

An example of a networking service that you can use to establish boundaries around your AWS resources is Amazon Virtual Private Cloud. (Amazon VPC).

Amazon VPC enables you to provision an isolated section of AWS Cloud. In this isolated section, you can launch resources in a virtual network that you define. Within a virtual private cloud (VPC), you can organise your resources into subnets. 

A _subnet_ is a section of a VPC that can contain resources such as Amazon EC2 instances.

## Internet Gateway
The internet gateway allows public traffic from the internet to access your VPC. You attach an internet gateway to the VPC.

An internet gateway is a connection between a VPC and the internet. You can see the internet gateway as a doorway that customers can use to enter your shop. 
Without an internet gateway, no one can access the resources within your VPC.

What if you have a VPC that includes only private resources?

## Virtual Private Gateway

An example of how a virtual private gateway works is you can think of the internet as the road between your home and the coffee shop. 

Suppose you are travelling on this road with a bodyguard to protect you. You are still using the same road as other customers, but with an extra layer of protection. 

The bodyguard is like a VPN connection that encrypts (or protects) your internet traffic from all other requests around it. 

The virtual private gateway is the component that allows protected internet traffic to enter into the VPC. Even though your connection to the shop has extra protection, traffic jams are possible because you're using the same road as other customers.

A virtual private gateway enables you to establish a virtual private network connection between your VPC and a private network, such as an on-premise data centre or internal corporate network. A VPG allows traffic into the VPC only if is coming from an approved network. 

## AWS Direct Connect
Is a service that enables you to establish a dedicated private connection between your data centre and a VPC.
 
An example would be suppose you are living in an apartment building with a hallway directly linking the building to the coffee shop. Only the residents of the apartment building can travel through this hallway. 

This private hallway provides the same type of dedicated connection as AWS Direct Connect. Residents are able to get into the coffee shop without needing to use the public road shared with other customers.

The private conenction that AWS Direct Connect provides helps you to reduce network costs and increase the amount of bandwidth that can travel through your network. 

## Subnets and Network Access Control Lists

### The role of Subnets in a VPC
The flow would be;
1. Customer gives their order to cashier
2. Cashier passes the order to the barista
3. Customer tries to cut the line and ask the barista for coffee
4. Flow of the queue gets distrupted and results in customers accessing areas of the coffee shop they shouldn't have access to.

To fix this issue, the coffee shop owner divides the counter area by placing the cashier and the barista in seperate workstations. 

The cashiers workstation is public facing and designed to receive customer orders. The barista area is private and out of sight of customers, solely to work on customer orders. The barister can receive orders directly from the cashier, but not the customers. 

This is similar to how you can use AWS networking services to isolate resources and determine exactly how network traffic flows.

In the coffee shop, you can think of the counter area as a VPC. The counter area divides into two seperate areas for the cashier's workstation and the barista's workstation. In a VPC, subnets are seperate areas that are used to group together resources. 

## Subnets
A subnet is a section of a VPC which you can group resources based on security or operational needs. Subnets can be public or private. 

Public subnets contain resources that need to be accessible by the public. An example would be an online store's website.

Private subnets contain resources that need to be accessed only through a private network. An example would be a database full of customer's personal information and order history. 

In a VPC, subnets can communicate with each other. For example, you might have an application that involves an EC2 instance in a public subnet communicating with databases that are located in a private subnet. 

## Network traffic in a VPC
When a customer requests data from an application hosted in AWS Cloud, this request is sent as a packet. A packet is a unit of data sent over the internet or a network. 

The packet enters into a VPC through an internet gateway. Before a packet can enter into a subnet or exit from a subnet, it checks for permissions. These permissions indicate who sent the packet and how the packet is trying to communicate with the resources in a subnet. 

The VPC component that checks the packet permissions for a subnet is called a Network Access Control List (ACLs)

## Network Access Control Lists (ACLs)
A Network Access Control List (ACL) is a virtual firewall that controls inbound and outbound traffic at a subnet level. 

For example, imagine you are in an airport. Travellers are trying to enter a new country at security. The travellers are the packets in this case, and the passport control officers as a network ACL. 
The passport control officer will check every travellers credentials when they are both entering and exiting out of the country. If a traveller is on the approved list, they will be allowed to enter. If not, they will be on a list of banned travellers and cannot enter. 

Each AWS account includes a default network ACL. When configuring your VPC, you can use your accounts default network ACL or create custom network ACLs. 

The default for AWS accounts allows all inbound and outbound traffic, but you can modify it by adding your own rules. For custom network ACLs, all inbound and outbound traffic is denied until you add rules to specify which traffic is allowed. Additionally, all network ACLs have an explicit deny rule. This rule ensures that if a packet does not match any of the other 






