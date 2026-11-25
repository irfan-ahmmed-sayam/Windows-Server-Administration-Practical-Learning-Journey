# Day 23 | Core Server Domain Join & Remote Role and Feature Installation

## Overview
In this practical session, we joined a Windows Server Core machine to an existing Active Directory Domain and explored how to remotely install Roles and Features from a Graphical Domain Controller using Server Manager.

## Lab Environment

| Server | Description | Role |
|---|---|---|
| Server 1 | Graphical Server | Domain Controller (DC) |
| CLI 1 | Windows Server Core | Member Server |
| Domain | abc.com | Active Directory Domain |

## Tasks Performed

### 1. Network Connectivity Verification
- Checked network connectivity between Server 1 and CLI 1.
- Verified connectivity using the `ping` command.
- Confirmed communication with the Domain Controller and domain name.

### 2. Core Server Domain Join
- Joined CLI 1 (Windows Server Core) to the existing `abc.com` domain.
- Used an authorized Domain User account for authentication.
- Successfully joined the Core Server to the domain.
- Verified the domain membership.

### 3. DHCP Server Role Installation
- Installed the DHCP Server Role on CLI 1.
- Verified successful installation of the DHCP Server Role.

### 4. Remote Role and Feature Installation
- Opened Server Manager on the Graphical Domain Controller.
- Connected to the remote Core Server.
- Remotely managed the Core Server.
- Installed Roles and Features on the Core Server using Server Manager.

## Video Demonstration

Watch the complete practical demonstration on YouTube:

**YouTube Video:** [Watch Day 23 Tutorial](https://youtu.be/RayzFNBMGm0)

## Learning Outcomes

- Understanding Active Directory Domain Join for Windows Server Core.
- Understanding the difference between a Domain Controller and a Member Server.
- Installing Server Roles on Windows Server Core.
- Managing and installing Roles and Features remotely using Server Manager.

---

**Project:** Windows Server Administration Practical Learning Journey  
**Day:** 23  
**Domain:** abc.com