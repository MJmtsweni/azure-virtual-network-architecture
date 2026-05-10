# Project 2: Azure Virtual Network Architecture

## Objective
Translate local networking fundamentals into Microsoft Azure cloud 
architecture, deploying a segmented virtual network with security 
controls and verified internal connectivity.

## Tools Used
- Microsoft Azure Portal
- Ubuntu Server 22.04 LTS
- SSH (Windows CMD)

## What I Built

### Virtual Network
Provisioned an Azure Virtual Network (Lab-VNet-AU) with a custom 
IPv4 address space of 10.0.0.0/16 and subnet segmentation.

### Virtual Machines
Deployed two Virtual Machines:
- Frontend-VM — public facing, with a public IP address
- Backend-VM — internal only, no public IP address

### Network Security Groups (NSGs)
Configured NSG inbound rules on Frontend-VM:
- Allowed inbound HTTP (port 80) from any source
- Allowed inbound HTTPS (port 443) from any source
- Allowed SSH (port 22) exclusively from home public IP
- Denied SSH (port 22) from all other sources

### Internal Connectivity
Verified internal VNet routing by successfully pinging Backend-VM 
from Frontend-VM using private IP addresses.

## Verification
- Frontend-VM successfully pings Backend-VM (10.0.0.5) ✅
- HTTP/HTTPS open to internet ✅
- SSH restricted to home IP only ✅
- Backend-VM has no public IP (private only) ✅

## Screenshots
- `nsg-rules.png` — NSG inbound rules for Frontend-VM
- `vnet-subnets.png` — Virtual Network subnet configuration
- `ping-success.png` — Successful ping from Frontend-VM to Backend-VM

## Key Learnings
- How Azure Virtual Networks provide logical network isolation
- How Network Security Groups act as stateful firewalls
- How subnets segment cloud resources into tiers
- How to restrict administrative access to specific IP addresses
- How internal VNet routing works between cloud VMs
