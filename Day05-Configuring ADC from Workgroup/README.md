# Day 05 | Windows Server 2016 | Installing & Configuring ADC from Workgroup

## 📌 Project Overview

In this lab, I practiced promoting a standalone Workgroup server (Server 3) to an Additional Domain Controller (ADC) in an existing Active Directory domain named `abc.com`.

I started by verifying that Server 3 was in a Workgroup. Then, I installed Active Directory Domain Services (AD DS), provided Domain Administrator credentials, and promoted Server 3 to an ADC.

Finally, I verified the successful promotion through Active Directory Users and Computers on Server 1.

## 🎯 Objectives

- Verify the existing Active Directory domain.
- Check the initial Workgroup status of Server 3.
- Install Active Directory Domain Services (AD DS).
- Promote a Workgroup server to an Additional Domain Controller.
- Configure the Directory Services Restore Mode (DSRM) password.
- Verify successful ADC promotion.

## 🖥️ Lab Environment

| Component | Configuration |
|---|---|
| Operating System | Windows Server 2016 |
| Domain Name | abc.com |
| Primary Domain Controller | Server 1 |
| Target Server | Server 3 |
| Initial Server Status | Workgroup |
| Final Server Role | Additional Domain Controller (ADC) |
| Virtualization Platform | VMware |

## ⚙️ Configuration Steps

### Step 1: Initial Verification

**Server 1 → Server Manager → Tools → Active Directory Users and Computers → abc.com**

1. Open the Domain Controllers container.
2. Verify that Server 1 is the existing Domain Controller.
3. Open the Computers container.
4. Verify that Server 3 is not listed.

### Step 2: Check Server 3 Status

**Server 3 → Server Manager → Local Server**

1. Open the Local Server dashboard.
2. Locate the Computer Name and Domain section.
3. Verify that Server 3 is currently connected to a Workgroup.

### Step 3: Install Active Directory Domain Services (AD DS)

**Server 3 → Server Manager → Manage → Add Roles and Features**

1. Navigate to Server Roles.
2. Select **Active Directory Domain Services (AD DS)**.
3. Click Add Features.
4. Continue through the installation wizard.
5. Click Install.

### Step 4: Promote Server 3 to Additional Domain Controller (ADC)

**Server 3 → Server Manager → Notifications → Promote this server to a domain controller**

1. Select **Add a domain controller to an existing domain**.
2. Enter the domain name: `abc.com`.
3. Provide Domain Administrator credentials.
4. Configure the Directory Services Restore Mode (DSRM) password.
5. Continue through the configuration wizard.
6. Review the configuration and click Install.

**Note:** Server 3 restarts automatically after the promotion process.

### Step 5: Final Verification

**Server 1 → Server Manager → Tools → Active Directory Users and Computers → abc.com**

1. Open the Domain Controllers container.
2. Verify that Server 3 now appears alongside Server 1.
3. Confirm that Server 3 has been successfully promoted as an Additional Domain Controller (ADC).

## 📚 Learning Outcomes

Through this practical lab, I gained hands-on experience with:

- Workgroup server identification.
- Active Directory Domain Services installation.
- Promoting a standalone server to an ADC.
- Existing domain authentication.
- DSRM password configuration.
- Additional Domain Controller verification.

## 🎥 Video Tutorial

[Watch on YouTube – Day 05: Installing & Configuring ADC from Workgroup](https://youtu.be/WQ3PDrMcL4w)

## 📁 Project Resources

- **GitHub Repository:** [Windows Server Administration](https://github.com/.../Windows-Server-Administration...)
- **YouTube Playlist:** [Windows Server Learning Journey](https://youtube.com/playlist?list=PLIEgi_iIRtLI...)

## 🚀 Conclusion

This practical lab helped me understand how to promote a server directly from a Workgroup environment to an Additional Domain Controller in an existing Active Directory domain.

It also strengthened my practical understanding of AD DS installation, domain authentication, and ADC deployment.

Another important step in my Windows Server Administration learning journey, focused on Active Directory infrastructure and domain controller management.

---

**#WindowsServer2016 #ActiveDirectory #ADDS #ADC #DomainController #Workgroup #SystemAdministration #ITInfrastructure #LearningJourney**