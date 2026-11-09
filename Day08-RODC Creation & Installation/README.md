# Day 08 | Windows Server 2016 | RODC Creation & Installation

## 📌 Project Overview

In this lab, I created and installed a **Read-Only Domain Controller (RODC)** in the `abc.com` domain using Windows Server 2016.

I first created a dedicated `RODCUser` account in Active Directory. Then, I pre-created the RODC computer account, installed Active Directory Domain Services (AD DS) on Server 2, and promoted Server 2 as an RODC.

Finally, I verified the RODC configuration in Active Directory Users and Computers.

## 🎯 Objectives

- Create a dedicated RODC user account.
- Pre-create an RODC computer account.
- Install Active Directory Domain Services (AD DS).
- Promote Server 2 as a Read-Only Domain Controller.
- Verify the RODC configuration.

## 🖥️ Lab Environment

| Component | Configuration |
|---|---|
| Operating System | Windows Server 2016 |
| Domain Name | abc.com |
| Server 1 | Existing Domain Controller (DC) |
| Server 2 | New Read-Only Domain Controller (RODC) |
| RODC User | RODCUser |
| Required Role | Active Directory Domain Services (AD DS) |

## ⚙️ Configuration Steps

### Step 1: Create RODC User

**Server 1 > Server Manager > Tools > Active Directory Users and Computers > Users**

1. Right-click **Users**.
2. Select **New > User**.
3. Enter the username: `RODCUser`.
4. Click Next.
5. Set the password.
6. Click Next > Finish.

### Step 2: Pre-Create RODC Account

**Server 1 > Active Directory Users and Computers > Domain Controllers**

1. Right-click **Domain Controllers**.
2. Select **Pre-Create Read-only Domain Controller Account**.
3. Select **Use advanced mode installation**.
4. Enter the computer name: `Server2`.
5. Continue through the configuration options.
6. Select the user account: `RODCUser`.
7. Complete the wizard by clicking Finish.

**Verification:** Server 2 appears in the Domain Controllers OU with a down status before promotion.

### Step 3: Install Active Directory Domain Services

**Server 2 > Server Manager > Add Roles and Features**

1. Click Next through the wizard.
2. Select **Active Directory Domain Services**.
3. Click **Add Features**.
4. Continue by clicking Next.
5. Click Install.

### Step 4: Promote Server 2 as RODC

**Server 2 > Server Manager > Notifications > Promote this server to a domain controller**

1. Select **Add a domain controller to an existing domain**.
2. Enter the domain: `abc.com`.
3. Click Change.
4. Enter the credentials: `abc.com\RODCUser`.
5. Click OK.
6. Set the Directory Services Restore Mode (DSRM) password.
7. Continue through the wizard.
8. Review the configuration and click Install.

**Result:** Server 2 restarts automatically after the promotion process.

### Step 5: Verify RODC Configuration

**Server 1 > Server Manager > Tools > Active Directory Users and Computers > Domain Controllers**

1. Refresh the Domain Controllers OU.
2. Verify that Server 2 appears in the list.
3. Confirm that Server 2 is configured as a Read-Only Domain Controller (RODC).

## 📚 Learning Outcomes

Through this practical lab, I learned how to:

- Create a dedicated RODC user account.
- Pre-create an RODC computer account using advanced mode.
- Install the AD DS role on a member server.
- Promote a server as a Read-Only Domain Controller.
- Verify the RODC configuration in Active Directory.

## 🎥 Video Tutorial

YouTube Video:  
https://youtu.be/JZoycPVpciM

## 📁 Project Resources

**GitHub Repository:**  
https://github.com/.../Windows-Server-Administration...

**YouTube Playlist:**  
https://youtube.com/playlist?list=PLIEgi_iIRtLI...

## 📝 Conclusion

This practical lab helped me understand the process of creating and installing a Read-Only Domain Controller (RODC) in a Windows Server 2016 environment.

It was another important step in my Windows Server Administration learning journey, helping me gain practical experience with Active Directory and RODC deployment.

## 🏷️ Tags

#WindowsServer2016 #ActiveDirectory #RODC #ReadOnlyDomainController #DomainController #SystemAdministration #ITInfrastructure #LearningJourney