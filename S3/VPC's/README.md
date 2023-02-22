

# VPC (Virtual Private network)

VPC is a concept in cloud computing that enables users to create a private virtual network within a public cloud environment.

It provides users with greater control over their resources and an added layer of security.


![](VPC.jpeg)

### Main Benefits of VPC's

1. Greater control: VPC provide the users with more control over their network infrastructure, including the ability to define their own IP address range, create subnets, configure routing tables and manage security settings.

2. Enhnaced security: VPC's offer an added layer of security by isolating resources from the public internet and other resources in the cloud environment.

3. Cost saving: VPC's can help reduce costs by allowing users to allocate and manage resources more efficiently.

4. FLexibility: VPCs are highly customizable and can be configured to support a wide range of use cases, including hosting web applications, running databases, and deploying virtual machines.

5. Improved performance: VPCs can help improve performance by enabling users to deploy resources in the regions that are closest to their end-users or customers. This can help reduce latency and improve application performance.



## How does it benefit the business ?

1. Improved security: VPC provides a secure environment for applications and data.

2. Cost savings: VPC can reduce costs by enabling efficient resource allocation.

3. Flexibility: VPC is customizable and can support a range of use cases.

4. Scalability: VPC allows businesses to easily scale their infrastructure up or down based on demand.

5. Improved performance: VPC can improve application performance by deploying resources in regions closest to end-users or customers.

## Benefits of VPC in DevOps

1. Security and compliance: private network environment for more secure and compliant deployments

2. Scalability: easy to scale infrastructure up or down based on demand

3. Automation: can automate infrastructure provisioning, configuration management, and deployment

4. Isolation: allows for separate management and troubleshooting of 

5. Collaboration: provides a centralized and secure network environment for improved collaboration and productivity.



# Subnets


A subnet is a smaller network within a larger network. It allows for more efficient use of IP addresses and helps to organize network resources into smaller groups. A subnet can be used to separate network traffic, control network access, and improve network security.


## Private and Public subnets

**Private subnets**:

Private subnets are used for resources that should not be directly accessible from the public internet, while public subnets are used for resources that need to be accessible from the internet. Private subnets typically do not have a public IP address and use a network address translation (NAT) gateway to communicate with the internet.

**Public subnets**:

Public subnets have a public IP address and can communicate directly with the internet. Private subnets are often used to host databases, internal application servers, or backend services, while public subnets are used for web servers or load balancers that need to be accessible from the internet.


# CIDR blocks

(A Classless Inter-domain Routing) is a range of IP addresses that can be used to allocate IP addresses more efficiently.

CIDR blocks allow for the creation of subnets with varying numbers of IP addresses. 

**Example**:

 CIDR block of 10.0.0.0/16 includes all IP addresses from 10.0.0.0 to 10.0.255.255, with the first 16 bits representing the network portion of the IP address


 # Internet Gateway

 An Internet Gateway is a service provided by cloud computing provides, whcih allows resources within a private network such as Virtual Private Cloud(VPC), to access public internet.

 When an instance in a private subnet needs access to the internet, it sends its traffic  to the internet gateway, which then routes the traffic to its destination. 



 ## Route tables

 A route table is a set of rules that determines how traffic is routed between a private network (such as a VPC) and other networks, such as the internet. The route table contains a list of destination IP addresses and the target for each route. By managing the rules in the route table, network administrators can control how traffic flows in and out of the VPC and between subnets within the VPC.