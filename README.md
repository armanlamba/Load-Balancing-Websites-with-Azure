# Load-Balancing-Websites-with-Azure

## Project Overview

This project involves building a load-balanced architecture for a private website using several Azure services. The goal is to distribute website traffic between two webservers via an Azure Internal Load Balancer. The project demonstrates key concepts like virtual networks, virtual machine creation, and configuring Azure Bastion and Private DNS zones.

### Architecture Components:
- **Azure Bastion**
- **Azure Virtual Machines** running IIS
- **Azure Virtual Networks**
- **Azure Load Balancer (Internal)**
- **Azure Virtual Network Peering**
- **Azure Private DNS Zones**

## Project Objectives

1. **Resource Group**: 
   - Create a resource group to logically organize all Azure resources.

2. **Virtual Networks**:
   - Set up two virtual networks with peering to connect different parts of the architecture.
   - Subnets are created for Bastion Host and the webservers.

3. **Load Balancer**:
   - Configure an internal load balancer to distribute traffic between two webservers.

4. **Azure Bastion**:
   - Use Azure Bastion to access the virtual machines securely without public IP addresses.

5. **Webservers**:
   - Deploy two virtual machines running IIS, each serving a unique default webpage to verify the load balancer's functionality.

6. **Private DNS Zone**:
   - Configure a Private DNS zone to allow access to the website via its Fully Qualified Domain Name (FQDN).

## Architecture Diagram

![Architecture Diagram](https://github.com/user-attachments/assets/fa02fce7-92b0-4f04-b818-94ec5e6049e2)





## Key Azure Services

- **Azure Bastion**: Provides secure access to virtual machines without exposing them to the public internet.
- **Azure Virtual Network**: Enables the communication between different Azure resources.
- **Azure Load Balancer**: Distributes incoming traffic across multiple virtual machines.
- **Azure Private DNS**: Allows domain-based name resolution in the virtual network without needing public DNS servers.

## Steps

### 1. Create a Resource Group
- Use the Azure portal to create a new resource group named `Rg-1`.

### 2. Configure Virtual Networks
- Set up two virtual networks (`vnet1` and `vnet2`) with appropriate subnets.
- Implement virtual network peering between them to allow communication.

### 3. Deploy and Configure the Load Balancer
- Create an internal load balancer in `vnet1`, configure backend pools, health probes, and load-balancing rules.

### 4. Deploy Virtual Machines (Webservers)
- Create two virtual machines (`webserver1-vm` and `webserver2-vm`) with Windows Server 2019 and IIS installed.
- Add them to the load balancer backend pool.

### 5. Set Up Azure Bastion
- Use Azure Bastion to access the virtual machines securely.

### 6. Configure Private DNS Zone
- Set up a private DNS zone to resolve the load balancer's IP to an FQDN.

## Testing

1. Use the Azure Bastion service to access the client VM.
2. In the client VM, open a browser and access the private website using the FQDN.
3. Refresh the page multiple times to ensure traffic is distributed between the two webservers.
