# Day 07 | Windows Server 2016 | Force Demotion of ADC & Metadata Cleanup

## 📌 Project Overview

In this lab, I practiced forcefully removing an Additional Domain Controller (ADC) from an existing Active Directory domain named `abc.com`.

After the forced demotion of Server 2, I performed metadata cleanup to remove its remaining information from Active Directory, DNS, and Active Directory Sites and Services.

Finally, I completed the cleanup process to remove the leftover Domain Controller records from the domain infrastructure.

## 🎯 Objectives

- Verify the existing Additional Domain Controller (ADC).
- Forcefully demote Server 2.
- Perform Active Directory metadata cleanup.
- Remove leftover DNS records.
- Remove Server 2 from Active Directory Sites and Services.
- Clean up the remaining Domain Controller information.

## 🖥️ Lab Environment

| Component | Configuration |
|---|---|
| Operating System | Windows Server 2016 |
| Domain Name | abc.com |
| Primary Domain Controller | Server 1 |
| Additional Domain Controller | Server 2 |
| Initial Server Role | Additional Domain Controller (ADC) |
| Cleanup Locations | Active Directory, DNS, Sites and Services |
| Virtualization Platform | VMware |

## ⚙️ Configuration Steps

### Step 1: Initial Verification

**Server 1 → Server Manager → Tools → Active Directory Users and Computers → abc.com → Domain Controllers**

1. Open the Domain Controllers container.
2. Verify that Server 2 is listed as an Additional Domain Controller (ADC).

### Step 2: Force Removal of Server 2

**Server 2 → Server Manager → Manage → Remove Roles and Features**

1. Navigate to Server Roles.
2. Uncheck **Active Directory Domain Services (AD DS)**.
3. Select Remove Features.
4. Click **Demote this domain controller**.
5. Enable **Force the removal of this domain controller**.
6. Click Next and select Proceed with removal.
7. Enter Local Administrator credentials.
8. Click Demote and complete the process.
9. Close the wizard.

**Note:** Server 2 restarts automatically after the forced demotion.

### Step 3: Metadata Cleanup – Active Directory

**Server 1 → Server Manager → Tools → Active Directory Users and Computers → abc.com → Domain Controllers**

1. Right-click Server 2.
2. Select Delete.
3. Confirm the deletion.
4. Enable **Delete this Domain Controller anyway and permanently remove the metadata**.
5. Click Delete.
6. Confirm the operation.

### Step 4: Metadata Cleanup – DNS

**Server 1 → Server Manager → Tools → DNS → Forward Lookup Zones → abc.com**

1. Locate the Server 2 DNS record.
2. Right-click the record.
3. Select Delete.
4. Confirm the deletion.

### Step 5: Metadata Cleanup – Active Directory Sites and Services

**Server 1 → Server Manager → Tools → Active Directory Sites and Services → Sites → Default-First-Site-Name → Servers**

1. Locate Server 2.
2. Right-click Server 2.
3. Select Delete.
4. Confirm the deletion.

## 📚 Learning Outcomes

Through this practical lab, I gained hands-on experience with:

- Additional Domain Controller (ADC) verification.
- Forced Domain Controller demotion.
- Active Directory metadata cleanup.
- DNS record management and cleanup.
- Active Directory Sites and Services management.
- Removing leftover Domain Controller information.

## 🎥 Video Tutorial

[Watch on YouTube – Day 07: Force Demotion of ADC & Metadata Cleanup](https://youtu.be/LmyyJsWwGwQ)

## 📁 Project Resources

- **GitHub Repository:** [Windows Server Administration](https://github.com/.../Windows-Server-Administration...)
- **YouTube Playlist:** [Windows Server Learning Journey](https://youtube.com/playlist?list=PLIEgi_iIRtLI...)

## 🚀 Conclusion

This practical lab helped me understand how to forcefully remove an Additional Domain Controller and perform metadata cleanup after an unsuccessful or forced demotion process.

I also practiced cleaning up leftover records from Active Directory, DNS, and Active Directory Sites and Services.

Another important step in my Windows Server Administration learning journey, focused on Domain Controller recovery and metadata management.

---

**#WindowsServer2016 #ActiveDirectory #ADC #ForceDemotion #MetadataCleanup #DNS #SystemAdministration #ITInfrastructure #LearningJourney**