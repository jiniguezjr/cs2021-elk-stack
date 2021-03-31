# CS2021-ELK-Stack 
> This project automates the installation and configuration of an ELK stack deployment on an Ubuntu 18.04 server. In this setup, there are a total of 4 Ubuntu 18.04 servers running on Azure. One server runs the ELK stack, the remaining three are web servers that are used to collect and monitor system resources and logs. Docker and Ansible are used to deploy and configure the web and elk servers.

## Architecture Diagram
<p align="center"><img src="https://github.com/jiniguezjr/cs2021-elk-stack/blob/main/Images/CS2021-Project-1-Architecture1.png" alt="CS2021 Project 1 ELK Stack Architecture Diagram" /></p>

## Architecture Overview
The main reason for this setup of 5 Ubuntu servers on the Azure platform is to have an environment that a Cybersecurity student can use to quickly deploy various servers and services which include:
1. three (3) DVWA web servers configured behind an HTTP load balancer with restricted public access

2. one (1) publicly-accessible SSH bastion server (jumpbox) that serves as a central management server for accessing and administering all the other servers on an internal network

3. one (1) publicly-accessible ELK server through HTTP that will collect and monitor system resources and logs of the three DVWA web servers

## Azure Setup
Since this was the first time using Azure, the network and server set up was done using the GUI. I will include screenshots of the important components, but, in a nutshell, these are the steps taken to setup the environment shown in the diagram.

1. Register for a free Azure account
 
- 30 day trial with 200$ credit and limit of 4 VMs per region

2. Create an Azure Resource Group to contain all related components of this project

- virtual machines, networks, load balancers, security groups

3. Create 2 virtual networks; one in West US 2, the other in Central US

- assign IP subnets for the servers

4. Create one Ubuntu bastion server with static IP

- install docker and configure it to run persistently
- install image, cyberxsecurity/ansible
- enter ansible image and generate root rsa pub/priv key pair

5. Create three Ubuntu servers using ansible public key and same user name on all three web servers

6. Create one Ubuntu ELK server with static IP

7. Install and configure DVWA and ELK on web and ELK servers using Ansible playbooks

### Azure Images
The images below visually represents all of the components needed to set up the servers (hardware, disks, ram, cpu, etc) and network components (subnets, firewalls, , network interfaces, load balancers, etc) required for this architecture. 

*The following points relate to the images below.*
1. The Azure Resource Group, CS2021_RG1, is a logical container that groups together related resources. Tags were added at this level in order to clearly identify resources that are related and to aid in properly associating costs to the right project or customer should you wish to group resources separately.
2. The virtual machines listed here are named according to their purpose and are placed in the appropriate location and with the minimum required hardware specs to fulfill it's role.
3. The network security groups.....
4. A virtual network peering connection is needed in order for resources in different locations (aka regions) to communicate to and from each location.
5. A load balancer was created to distribute the HTTP traffic amongst the three web servers. A backend pool was configured and is what receives the public IP address which can be configured to resolve using a DNS A or CNAME record (e.g. www.hack-me.com)
#### 1. Azure Resource Group Items
<p align="center"><img src="https://github.com/jiniguezjr/cs2021-elk-stack/blob/main/Images/ELK-stack-project-1-Azure-resource-group-list.png" alt="Azure Resource Group List" /></p>

#### 2. Azure Virtual Machines
<p align="center"><img src="https://github.com/jiniguezjr/cs2021-elk-stack/blob/main/Images/ELK-stack-project-1-Azure-VM-list.png" alt="Azure Virtual Machines" /></p>

#### 3. Azure Network Security Groups
<p align="center"><img src="https://github.com/jiniguezjr/cs2021-elk-stack/blob/main/Images/ELK-stack-project-1-Azure-main-net-sec-group-rules.png" alt="Azure Network Security Group Rules" /></p>

#### 4. Azure Virtual Networks Peering Setup
<p align="center"><img src="https://github.com/jiniguezjr/cs2021-elk-stack/blob/main/Images/ELK-stack-project-1-Azure-virtual-networks-peering-setup.png" alt="Azure Virtual Networks Peering Setup" /></p>

#### 5. Azure Load Balancer Backend Pool 
<p align="center"><img src="https://github.com/jiniguezjr/cs2021-elk-stack/blob/main/Images/ELK-stack-project-1-Azure-load-balancer-backend-pool.png" alt="Azure Load Balancer Backend Pool" /></p>

## Ansible Provisioner Setup 

## DVWA Server Setup

## ELK Server Setup 
### ELK Configuration
### ELK + Beats Setup
## Security Access Policies

## Author

I'm [Jesse Iniguez Jr](https://www.linkedin.com/in/jesseiniguez/), and I approve of this repository. :)
