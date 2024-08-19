# Azure Networking

## Virtual Network (VNet)
A Virtual Network (VNet) in Azure is like a private network for your resources in the cloud. It keeps them secure and lets them communicate with each other, and even with resources outside of Azure. Think of it as creating a private area for your cloud stuff, separate from everyone else's.

- **Isolation**: This is about keeping your resources separate from others, kind of like having your own private Wi-Fi network at home.
- **Subnetting**: You can split your VNet into smaller sections (subnets) to organize your resources better and manage how they talk to each other.
- **Address Space**: This is just the range of IP addresses your VNet can use, like deciding what numbers your devices at home will use to talk to each other.

## Subnets
Subnets are smaller sections within a VNet. Imagine you have different rooms in your house, and each room is for something specific—like one for work and one for entertainment. Subnets help you organize your resources in a similar way.

## CIDR (Classless Inter-Domain Routing)
CIDR is a way to describe a range of IP addresses, like saying "this neighborhood covers house numbers 1 to 100." It helps you define which IP addresses your VNet or subnet will use.

## Routes and Route Tables
- **Routes**: These are like maps that tell your network traffic where to go, similar to giving someone directions to reach a destination.
- **Route Tables**: These are collections of routes, like having a list of all possible directions for traffic. You can use these tables to manage how traffic moves around your VNet.

## Network Security Groups (NSGs)
NSGs are like security guards for your network. They decide what kind of traffic is allowed in or out of your network resources.

- **Rules**: These are the instructions that tell the security guards what to let through and what to block, based on things like the source and destination of the traffic.
- **Default Rules**: These are the basic rules that come with every NSG, which help control traffic between different parts of your VNet.
- **Association**: You can assign these security guards (NSGs) to either whole subnets or to individual network interfaces (the connections for each resource).

## Application Security Groups (ASGs)
ASGs make it easier to manage security by grouping your resources based on their role or function.

- **Simplification**: Instead of managing security for each individual IP address, you can manage it for a group of resources that do the same thing.
- **Dynamic Membership**: You can automatically add resources to an ASG based on certain tags or attributes, making it easier to keep things organized.
- **Rule Association**: You can apply security rules to ASGs, so you don't have to worry about setting them up individually for each resource.
