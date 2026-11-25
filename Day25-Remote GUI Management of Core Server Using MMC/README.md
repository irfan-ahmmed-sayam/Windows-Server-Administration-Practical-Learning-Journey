# Day 25 – Remote GUI Management of Core Server Using MMC

## Overview

In this lab, I explored how to remotely manage specific services of a Windows Server Core (CLI) using Microsoft Management Console (MMC) from a server with a graphical user interface.

The practical demonstration focuses on accessing and managing the Disk Management console of **CLI 1 (Core Server)** remotely from **Server 1 (Domain Controller)**.

## Lab Environment

| Server | Role / Description |
|---|---|
| Server 1 | Domain Controller (DC) – Graphical User Interface (GUI) |
| CLI 1 | Windows Server Core – Command-Line Interface (CLI) |
| Management Tool | Microsoft Management Console (MMC) |
| Managed Service | Disk Management |
| Management Type | Remote GUI Management |

## Requirements and Preparation

- Review the requirements for managing a Server Core installation through MMC.
- Join CLI 1 (Core Server) to the domain.
- Understand the benefits of domain membership for security and authentication.
- Verify the domain connection between Server 1 (DC) and CLI 1 (Core Server).

## Configuration Steps

### 1. Verify the Domain Connection

Verify that CLI 1 (Core Server) is successfully joined to the domain and that it can be managed from Server 1 (DC).

### 2. Configure MMC

1. Open Microsoft Management Console (MMC) on Server 1.
2. Add the **Disk Management** snap-in.
3. Use **File > Save As** to save the MMC console on the Desktop.

### 3. Access Remote Disk Management

Use the saved MMC console on Server 1 to access the Disk Management console of CLI 1 (Core Server).

After completing the configuration, Disk Management for CLI 1 can be accessed remotely from Server 1 through a graphical interface.

## Infographic

The infographic below illustrates the remote MMC management setup.

![MMC Server Management Infographic](MMC%20Server%20Management%20Infographic.png)

> **Image file:** `MMC Server Management Infographic.png`  
> Keep the image in the same folder as this README file. If you store it in a different folder, update the image path above.

## YouTube Video

Watch the practical demonstration:

**YouTube Video:** [Add YouTube video link here](https://youtu.be/50O6ewWR4Z4)

## Learning Outcome

Through this hands-on practice, I learned how to use MMC from a GUI-based server to access and manage the Disk Management console of a Windows Server Core installation remotely.

This documentation is part of my ongoing Windows Server practical learning journey and is maintained for future reference.

---

**Topics:** Windows Server, Server Core, MMC, Remote Management, Disk Management, Domain Controller, Active Directory
