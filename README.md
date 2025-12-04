
1. Overview of the VPC Architecture

I have chosen to create a unique Virtual Private Cloud (VPC), with an IP Addressing Scheme that is structured and scalable, using the CIDR Block 10.0.0.0/16.

This allows for ample private IPv4 Address Space (Internet Protocol Version 4) for growth and flexibility.

In the VPC I created 4 subnets, 2 being Public (i.e., access to the internet via an Internet Gateway) and 2 being Private (i.e., no direct access to the internet via a NAT Gateway) located within separate Availability Zones (AZ’s) for the purpose of high availability (HA).

The Public Subnets will have access to the internet through an Internet Gateway and the Private Subnets will have internet access secured through a NAT Gateway, which is located within a Public Subnet.

The design has been created using best practice technical standards from the AWS cloud provider for secure production quality networking.

2. VPC & Subnet CIDR Range
Component Name CIDR Block Usage
VPC Khushi_Awasthi_VPC 10.0.0.0/16 Full network range
Public Subnet 1 PublicSubnet1 10.0.1.0/24 Public resources (AZ1)
Public Subnet 2 PublicSubnet2 10.0.2.0/24 Public resources (AZ2)
Private Subnet 1 PrivateSubnet1 10.0.3.0/24 Private workloads (AZ1)
Private Subnet 2 PrivateSubnet2 10.0.4.0/24 Private workloads (AZ2)

Reasoning Behind Choose CIDR:

The CIDR Block size of /24 will allow 256 usable IP addresses (Usable = 254) in each subnet which will meet the requirements of small to medium workload capacity.

The IT Design remains clean and predictable using sequential ranges.

By utilizing AZ’s for evenly distributed subnet allocation, we are providing for fault tolerance.

Privately allocated subnets will protect the back-end resources.
