# CS2021-ELK-Stack 
> This project automates the installation and configuration of an ELK stack deployment on an Ubuntu 18.04 server. In this setup, there are a total of 4 Ubuntu 18.04 servers running on Azure. One server runs the ELK stack, the remaining three are web servers that are used to collect and monitor system resources and logs. Docker and Ansible are used to deploy and configure the web and elk servers.

## Architecture Diagram
<p align="center"><img src="https://github.com/jiniguezjr/cs2021-elk-stack/blob/main/Images/CS2021-Project-1-Architecture1.png" width="1000" height="800" alt="CS2021 Project 1 ELK Stack Architecture Diagram" /></p>

## Architecture Overview
The main reason for this setup of 5 Ubuntu servers on the Azure platform is to have an environment that a Cybersecurity student can use to quickly deploy various servers and services which include:
- three DVWA web servers configured behind an HTTP load balancer with restricted public access
- a publicly-accessible SSH bastion server (jumpbox) that serves as a central management server for accessing and administering all the other servers on an internal network
- a publicly-accessible ELK server through HTTP that will collect and monitor system resources and logs of the three DVWA web servers


## Azure Setup


## Ansible Provisioner Setup 


## DVWA Server Setup

## ELK Server Setup 
### ELK Configuration
### ELK + Beats Setup
## Security Access Policies

## Author

I'm [Jesse Iniguez Jr](https://www.linkedin.com/in/jesseiniguez/), and I approve of this repository.
