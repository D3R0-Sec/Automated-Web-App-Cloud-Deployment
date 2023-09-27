# Cloud-Network-Deployment
## Overview

A personal project to setup a cloud network infrastructure, with exposed DVWA (Damn Vulnerable Web App) running behind a load balancer, using Azure services.

The objective of this project was to use Azure Cloud Services to setup an entire hypothetical cloud network infrastructure with two vulnerable DVWA web apps. The purpose of the load balancer was to ensure availability and also to control traffic coming into the servers.

Contained herein this readme are the steps taken and files used to setup the network displayed below.

A horizontally scalable web server was provisioned using this custom written ansible playbooks in yaml:



![Reed_Williams_Cloud_Security (1)](https://github.com/rwilliams1026/Cloud-Network-Deployment/assets/123021812/7a2b5a5a-7152-4cfd-bd44-881da4b182fd)

## Deployment
I began by setting up a resource group to better help organize all of the infrastructure into one manageable group.

![Screenshot 2023-09-26 173949](https://github.com/rwilliams1026/Cloud-Network-Deployment/assets/123021812/78cb5ca4-98a7-44b0-9901-341af9382292)

I then set up a Virtual Network with an ip range of 10.0.0.0/16 and a subnet of 10.0.1.0/24

![Screenshot 2023-09-26 174544](https://github.com/rwilliams1026/Cloud-Network-Deployment/assets/123021812/3a8e085d-d762-45b9-a807-f2ec51e7f3bb)

Next a Network Security Group was setup to provide a firewall for incoming traffic.

![Screenshot 2023-09-26 183943](https://github.com/rwilliams1026/Cloud-Network-Deployment/assets/123021812/9ad2f54c-66d9-455c-966d-868fde7a4743)

Using a "fan-in" topology pattern I deployed a central jumpbox to act as a gateway to our web server.

Using an ansible docker image on the jumpbox to horizontally scale and provision the web server VMs through containerization.


