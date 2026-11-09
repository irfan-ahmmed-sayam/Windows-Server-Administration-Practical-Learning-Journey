# Day 08 | Windows Server 2016 | RODC Creation & Installation

## 📌 Project Overview

In this lab, I practiced creating and installing a **Read-Only Domain Controller (RODC)** in a Windows Server 2016 environment.

I created a dedicated RODCUser account in Active Directory, pre-created the RODC computer account, installed Active Directory Domain Services (AD DS) on Server 2, and promoted Server 2 as an RODC in the `abc.com` domain.

Finally, I verified the RODC configuration through Active Directory Users and Computers.

## 🎯 Objectives

- Create a dedicated RODCUser account.
- Pre-create an RODC computer account.
- Install Active Directory Domain Services (AD DS).
- Promote Server 2 as a Read-Only Domain Controller.
- Verify the RODC configuration.

## 🖥️ Lab Environment

| Component | Configuration |
|---|---|
| Operating System | Windows Server 2016 |
| Domain Name | abc.com |
| Primary Domain Controller | Server 1 |
| Read-Only Domain Controller | Server 2 |
| RODC User Account | RODCUser |
| Virtualization Platform | VMware |

## ⚙️ Configuration Steps

### Step 1: Create RODC User Account

**Server 1 → Server Manager → Tools → Active Directory Users and Computers → Users**

1. Right-click **Users**.
2. Select New → User.
3. Enter the username: `RODCUser`.
4. Set a password.
5. Complete the wizard.

### Step 2: Pre-Create RODC Computer Account

**Server 1 → Active Directory Users and Computers → Domain Controllers**

1. Right-click Domain Controllers.
2. Select **Pre-Create Read-only Domain Controller Account**.
3. Enable **Use advanced mode installation**.
4. Enter the computer name: `Server2`.
5. Select the previously created `RODCUser` account.
6. Complete the configuration wizard.

**Verification:** Server 2 appears in the Domain Controllers OU with a down status.

### Step 3: Install Active Directory Domain Services

**Server 2 → Server Manager → Add Roles and Features**

1. Follow the installation wizard.
2. Select **Active Directory Domain Services (AD DS)**.
3. Click Add Features.
4. Continue through the wizard.
5. Click Install.

### Step 4: Promote Server 2 as RODC

**Server 2 → Server Manager → Notifications → Promote this server to a domain controller**

1. Select **Add a domain controller to an existing domain**.
2. Enter the domain name: `abc.com`.
3. Provide the `RODCUser` credentials.
4. Select the RODC configuration.
5. Set the Directory Services Restore Mode (DSRM) password.
6. Complete the configuration wizard.
7. Click Install.

**Note:** Server 2 restarts automatically after the promotion process.

### Step 5: Verify RODC Configuration

**Server 1 → Server Manager → Tools → Active Directory Users and Computers → Domain Controllers**

1. Refresh the Domain Controllers OU.
2. Locate Server 2.
3. Verify that Server 2 is configured as a Read-Only Domain Controller (RODC).

## 📚 Learning Outcomes

Through this practical lab, I gained hands-on experience with:

- RODC account pre-creation.
- RODC user account configuration.
- Active Directory Domain Services installation.
- Domain controller promotion.
- RODC deployment and verification.

## 🎥 Video Tutorial

[Watch on YouTube – Day 08: RODC Creation & Installation](https://youtu.be/JZoycPVpciM)

## 🚀 Conclusion

This practical lab helped me understand the deployment process of a Read-Only Domain Controller in a Windows Server 2016 environment.

Another important step in my Windows Server Administration learning journey, focused on Active Directory infrastructure and RODC deployment.

---

**#WindowsServer2016 #ActiveDirectory #RODC #ReadOnlyDomainController #SystemAdministration #ITInfrastructure #LearningJourney**
