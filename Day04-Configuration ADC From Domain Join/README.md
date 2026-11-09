# Day 04 | Windows Server 2016 | Additional Domain Controller (ADC) Installation & Configuration

## 📌 Project Overview

In this lab, I practiced installing Active Directory Domain Services (AD DS) and promoting an existing Member Server (Server 2) to an Additional Domain Controller (ADC) in the `abc.com` domain.

After the promotion process, I verified the ADC configuration through Active Directory Users and Computers. I also created VMware snapshots to save the current lab configuration.

## 🎯 Objectives

- Verify the existing Member Server configuration.
- Install Active Directory Domain Services (AD DS).
- Promote Server 2 to an Additional Domain Controller (ADC).
- Verify successful ADC configuration.
- Create VMware snapshots of the lab environment.

## 🖥️ Lab Environment

| Component | Configuration |
|---|---|
| Operating System | Windows Server 2016 |
| Domain Name | abc.com |
| Primary Domain Controller | Server 1 |
| Member Server / ADC | Server 2 |
| Server 2 Initial Role | Member Server |
| Server 2 Final Role | Additional Domain Controller |
| Virtualization Platform | VMware |

## ⚙️ Configuration Steps

### Step 1: Initial Verification

**Server 1 → Server Manager → Tools → Active Directory Users and Computers → abc.com**

1. Open the Domain Controllers container.
2. Verify that Server 2 is not listed.
3. Open the Computers container.
4. Verify that Server 2 exists as a Member Server.

### Step 2: Install Active Directory Domain Services (AD DS)

**Server 2 → Server Manager → Manage → Add Roles and Features**

1. Navigate to Server Roles.
2. Select **Active Directory Domain Services (AD DS)**.
3. Click Add Features.
4. Continue through the installation wizard.
5. Click Install.

### Step 3: Promote Server 2 to Additional Domain Controller (ADC)

**Server 2 → Server Manager → Notifications → Promote this server to a domain controller**

1. Select **Add a domain controller to an existing domain**.
2. Enter the domain name: `abc.com`.
3. Configure the Directory Services Restore Mode (DSRM) password.
4. Continue through the configuration wizard.
5. Review the configuration and click Install.

**Note:** Server 2 restarts automatically after the promotion process.

### Step 4: Final Verification

**Server 1 → Server Manager → Tools → Active Directory Users and Computers → abc.com**

1. Open the Domain Controllers container.
2. Verify that Server 2 now appears alongside Server 1.
3. Open the Computers container.
4. Verify that Server 2 is no longer listed as a regular Member Server.

### Step 5: Create VMware Snapshots

**VMware → Right-click Virtual Machine → Snapshot → Take Snapshot**

1. Select the virtual machine.
2. Open Snapshot options.
3. Click Take Snapshot.
4. Enter the snapshot name: `ADC Create`.
5. Save the snapshot.
6. Repeat the process for Server 1 and other lab devices.

## 📚 Learning Outcomes

Through this practical lab, I gained hands-on experience with:

- Member Server verification.
- Active Directory Domain Services installation.
- Additional Domain Controller (ADC) promotion.
- Existing domain controller infrastructure.
- Active Directory verification.
- VMware snapshot creation and lab configuration backup.

## 🎥 Video Tutorial

[Watch on YouTube – Day 04: Additional Domain Controller (ADC) Installation & Configuration](https://youtu.be/7-ZiPz4BwSU)

## 📁 Project Resources

- **GitHub Repository:** [Windows Server Administration](https://github.com/.../Windows-Server-Administration...)
- **YouTube Playlist:** [Windows Server Learning Journey](https://youtube.com/playlist?list=PLIEgi_iIRtLI...)

## 🚀 Conclusion

This practical lab helped me understand how to convert an existing Member Server into an Additional Domain Controller within an existing Active Directory domain.

I also practiced verifying domain controller roles and creating VMware snapshots to preserve the lab environment.

Another important step in my Windows Server Administration learning journey, focused on Active Directory infrastructure and domain controller management.

---

**#WindowsServer2016 #ActiveDirectory #ADDS #ADC #DomainController #VMware #SystemAdministration #ITInfrastructure #LearningJourney**