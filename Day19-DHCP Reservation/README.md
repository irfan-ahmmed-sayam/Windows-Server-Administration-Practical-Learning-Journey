# Day 19 | Windows Server | DHCP Reservation (MAC Binding)

## 📌 Overview

In this lab, I practiced **DHCP Reservation (MAC Binding)** in Windows Server 2016 using two different methods.

DHCP Reservation allows a DHCP server to assign a specific IP address to a particular device based on its MAC address. This ensures that the device receives the same IP address whenever it requests an IP from the DHCP server.

## 🎯 Lab Objectives

- Understand DHCP Reservation (MAC Binding).
- Configure DHCP Reservation using an existing DHCP Lease.
- Configure DHCP Reservation using a MAC Address.
- Verify DHCP Reservation configurations.
- Confirm that clients receive their assigned IP addresses.

## ⚙️ Practical Configuration

### Method 1: Reservation Using Existing DHCP Lease

In this method, Client 1 first obtains an IP address automatically from the DHCP Server.

**Configuration Steps:**

1. Client 1 → Obtain an IP address from DHCP.
2. Server 1 → Server Manager → Tools → DHCP.
3. IPv4 → Address Leases.
4. Find Client 1's existing DHCP Lease.
5. Right-click the lease → Add to Reservation.

**Result:** The existing DHCP IP address is reserved for Client 1 without manually entering its MAC address.

### Method 2: Reservation Using MAC Address

In this method, I manually collected the MAC address of Server 3 and created a reservation from the DHCP Server.

**Configuration Steps:**

1. Server 3 → Collect the MAC Address.
2. Server 1 → Server Manager → Tools → DHCP.
3. IPv4 → Reservations.
4. Right-click Reservations → New Reservation.
5. Enter the Reservation Name.
6. Enter the desired IP Address.
7. Enter the collected MAC Address.
8. Select the appropriate supported DHCP client type and save the reservation.

**Result:** A specific IP address is assigned to Server 3 based on its MAC address.

## ✅ Configuration Verification

After completing both reservation methods, I verified the configurations.

- Checked both reservations in the DHCP Management Console.
- Verified Client 1 received its reserved IP address.
- Verified Server 3 received its manually assigned reserved IP address.
- Confirmed that both devices received their expected IP addresses.

## 📚 Key Learning Points

- DHCP Reservation
- MAC Address Binding
- DHCP Address Leases
- Manual MAC Address Configuration
- DHCP Server Management
- DHCP Configuration Verification

## 🖥️ Lab Environment

- **Operating System:** Windows Server 2016
- **DHCP Server:** Server 1
- **Client Device:** Client 1
- **Additional Server:** Server 3
- **Service:** DHCP Server

## 🎥 YouTube Video

[▶️ Watch the Practical Configuration Video](https://youtu.be/v2nJ_8Ac8-I)

## 📂 Documentation

This repository contains the practical documentation and configuration steps from my Windows Server 2016 learning journey.

---

**Day 19 Completed | Windows Server 2016 Practical Lab**