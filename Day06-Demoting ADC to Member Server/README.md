# Day 06 | Windows Server 2016 | Demoting Domain Controller to Member Server

## 📌 Project Overview

In this lab, I practiced demoting an Additional Domain Controller (ADC) back to a Member Server in a Windows Server 2016 environment.

I removed the Active Directory Domain Services (AD DS) role from Server 2 and completed the domain controller demotion process. After the demotion, I verified that Server 2 was removed from the Domain Controllers container and appeared in the Computers container in Active Directory.

## 🎯 Objectives

- Verify the existing Additional Domain Controller (ADC).
- Remove Active Directory Domain Services (AD DS).
- Demote Server 2 from ADC to Member Server.
- Configure a new Local Administrator password.
- Verify the successful demotion.
- Confirm Server 2 appears as a Member Server.

## 🖥️ Lab Environment

| Component | Configuration |
|---|---|
| Operating System | Windows Server 2016 |
| Domain Name | abc.com |
| Primary Domain Controller | Server 1 |
| Target Server | Server 2 |
| Initial Server Role | Additional Domain Controller (ADC) |
| Final Server Role | Member Server |
| Virtualization Platform | VMware |

## ⚙️ Configuration Steps

### Step 1: Initial Verification

**Server 1 → Server Manager → Tools → Active Directory Users and Computers → abc.com**

1. Open the Domain Controllers container.
2. Verify that Server 2 is listed as a Domain Controller.
3. Open the Computers container.
4. Verify that Server 2 is not listed as a Member Server.

### Step 2: Remove Active Directory Domain Services (AD DS)

**Server 2 → Server Manager → Manage → Remove Roles and Features**

1. Continue through the installation wizard.
2. Navigate to Server Roles.
3. Uncheck **Active Directory Domain Services (AD DS)**.
4. Select Remove Features.

### Step 3: Demote Server 2 to Member Server

1. Select **Demote this domain controller**.
2. Click Next.
3. Select Proceed with removal.
4. Continue through the wizard.
5. Set a new Local Administrator password.
6. Click Demote.
7. Complete the process and close the wizard.

**Note:** Server 2 restarts automatically after the demotion process.

### Step 4: Final Verification

**Server 1 → Server Manager → Tools → Active Directory Users and Computers → abc.com**

1. Open the Domain Controllers container.
2. Verify that Server 2 is no longer listed.
3. Open the Computers container.
4. Verify that Server 2 now appears as a Member Server.

## 📚 Learning Outcomes

Through this practical lab, I gained hands-on experience with:

- Additional Domain Controller (ADC) verification.
- Active Directory Domain Services removal.
- Domain Controller demotion.
- Local Administrator password configuration.
- Member Server configuration.
- Active Directory container verification.

## 🎥 Video Tutorial

[Watch on YouTube – Day 06: Demoting Domain Controller to Member Server](https://youtu.be/a3uy_dFARmY)

## 📁 Project Resources

- **GitHub Repository:** [Windows Server Administration](https://github.com/.../Windows-Server-Administration...)
- **YouTube Playlist:** [Windows Server Learning Journey](https://youtube.com/playlist?list=PLIEgi_iIRtLI...)

## 🚀 Conclusion

This practical lab helped me understand how to demote an Additional Domain Controller and convert it back into a Member Server within an existing Active Directory domain.

I also practiced removing AD DS and verifying the changes through Active Directory Users and Computers.

Another important step in my Windows Server Administration learning journey, focused on Domain Controller role management and Active Directory administration.

---

**#WindowsServer2016 #ActiveDirectory #ADDS #DomainController #MemberServer #SystemAdministration #ITInfrastructure #LearningJourney**