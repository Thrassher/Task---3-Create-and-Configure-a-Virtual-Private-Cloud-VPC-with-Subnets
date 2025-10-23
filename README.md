Task 3: Create and Configure a Virtual Private Cloud (VPC) with Subnets



Objective :-
•	To understand how cloud networking works by creating a Virtual Private Cloud (VPC) with public and private subnets, and configuring controlled internet access.
•	This task demonstrates the foundation of secure cloud architecture, focusing on network isolation, routing, and resource protection.

Steps to Implement :-
1. Create a VPC
•	Go to the VPC Dashboard in your cloud provider (e.g., AWS).
•	Click Create VPC → Select VPC only.
•	Provide:
o	Name: Task-3
o	IPv4 CIDR block: 10.0.0.0/16
•	Click Create VPC.
2. Create Subnets :-
a) Public Subnet
•	Go to Subnets → Create Subnet.
•	Choose your VPC.
•	Enter details:
o	Subnet name: Task-3-Subnet-Public
o	Availability Zone: Select one (e.g., ap-south-1a)
o	CIDR block: 10.0.1.0/24
•	Click Create Subnet.

b) Private Subnet
•	Repeat the process for:
o	Subnet name: Task-3-Subnet-Private
o	CIDR block: 10.0.2.0/24
3. Create and Attach an Internet Gateway :-
•	Navigate to Internet Gateways → Create Internet Gateway.
•	Name it Task-3-Gateway and click Create.
•	Attach it to your VPC using Actions → Attach to VPC.

4. Configure Route Tables :-
a) Public Route Table
•	Go to Route Tables → Create Route Table.
•	Name: Task-3-Public, associate it with your VPC.
•	Under Routes, add:
o	Destination: 0.0.0.0/0
o	Target: Internet Gateway (MyIGW)
•	Under Subnet Associations, associate Public-Subnet.
b) Private Route Table
•	Create another route table named Task-3-Private
•	Do not add an internet route.
•	Associate it with Private-Subnet.


4. Launch EC2 Instances
•	Public EC2 Instance:
o	Launch in Public-Subnet

•	Private EC2 Instance:
o	Launch in Private-Subnet



5. Test Connectivity
•	SSH into your Public EC2 (using its public IP).








