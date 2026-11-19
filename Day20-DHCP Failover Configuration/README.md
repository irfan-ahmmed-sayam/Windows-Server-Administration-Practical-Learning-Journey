# Day 20 – DHCP Failover Configuration (Load Balance Mode)

## 📌 Project Overview

In this lab, I configured **DHCP Failover** between two Windows Server machines to improve DHCP service availability and reliability.

The main objective was to configure a secondary DHCP server that can continue providing IP addresses to client machines when the primary DHCP server becomes unavailable.

## 🖥️ Lab Scenario

This lab uses two servers:

| Server | Role |
|---|---|
| Server 1 | Primary DHCP Server |
| Server 2 | Secondary / Failover Server |

## ⚙️ Topics Covered

- Introduction to DHCP Failover.
- Understanding DHCP Failover modes.
- Load Balance Mode.
- Hot Standby Mode.
- Differences between Load Balance and Hot Standby.
- DHCP Failover configuration.
- Establishing a failover relationship between two DHCP servers.
- Practical DHCP Failover testing and verification.

## 🔄 DHCP Failover Modes

### 1. Load Balance Mode

In Load Balance Mode, both DHCP servers actively provide IP addresses to client machines and share the DHCP workload.

### 2. Hot Standby Mode

In Hot Standby Mode, one DHCP server works as the active server, while the second server remains on standby and takes over when the primary server becomes unavailable.

**Selected Configuration:** Load Balance Mode

## 🛠️ Configuration Steps

1. Configure Server 1 as the Primary DHCP Server.
2. Prepare Server 2 as the Failover Server.
3. Open the DHCP management console.
4. Select the DHCP scope on Server 1.
5. Configure DHCP Failover.
6. Add Server 2 as the partner server.
7. Select Load Balance Mode.
8. Complete the failover configuration.
9. Verify the failover relationship between both servers.

## 🧪 Practical Failover Verification

After completing the configuration, I performed a practical test to verify that DHCP Failover was working correctly.

**Testing Procedure:**

1. Opened the DHCP management console on Server 1.
2. Disabled the DHCP Scope on Server 1 (Primary DHCP Server).
3. Checked IP address allocation from the client machines.
4. Verified that Server 2 (Failover Server) successfully provided IP addresses to the clients.

**Expected Result:**

Even when the DHCP Scope on Server 1 was disabled, Server 2 successfully provided IP addresses to the client machines.

This confirmed that the DHCP Failover configuration was working as expected.

## 🎯 Learning Outcomes

Through this practical lab, I learned:

- How DHCP Failover works.
- The differences between Load Balance and Hot Standby modes.
- How to configure DHCP Failover between two servers.
- How to verify DHCP service availability.
- How a secondary DHCP server can provide IP addresses when the primary server becomes unavailable.

## 📸 Configuration Documentation

Screenshots of the configuration process and practical verification are included in this repository for step-by-step reference.

## 🎥 YouTube Video

[Watch the Full Configuration & Practical Demonstration](https://youtu.be/wQ_d1vQhd4U)

## 📝 Project Information

This lab is part of my Windows Server practical learning journey. All configurations and testing procedures are documented for future reference and hands-on practice.

---

**Topics:** Windows Server | DHCP | DHCP Failover | Load Balance Mode | Hot Standby Mode | High Availability | Networking