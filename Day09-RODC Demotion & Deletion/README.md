# Day 09 | Windows Server 2016 | RODC Demotion & Deletion

## 📌 Project Overview

In this lab, I practiced two important Read-Only Domain Controller (RODC) management tasks in Windows Server 2016.

**Topic 1: RODC Demotion**  
I demoted Server 2 from an RODC to a Workgroup server and performed metadata cleanup in Active Directory.

**Topic 2: RODC Deletion (Metadata Cleanup)**  
I restored a previously created RODC snapshot to simulate an inaccessible RODC scenario. Then, I removed its computer account and related metadata from Active Directory and verified the result.

## 🎯 Objectives

- Demote an RODC from the domain.
- Convert Server 2 into a Workgroup server.
- Perform Active Directory metadata cleanup.
- Remove an inaccessible RODC from Active Directory.
- Clean up the related records in Active Directory Sites and Services.
- Verify the RODC deletion.

## 🖥️ Lab Environment

| Component | Configuration |
|---|---|
| Operating System | Windows Server 2016 |
| Domain Name | abc.com |
| Server 1 | Main Domain Controller (DC) |
| Server 2 | Read-Only Domain Controller (RODC) |
| User Account | RODCUser |
| Management Tools | ADUC, Active Directory Sites and Services |

---

# ⚙️ Topic 1: RODC Demotion

## Step 1: Initial Verification

**Server 1 > Server Manager > Tools > Active Directory Users and Computers > abc.com > Domain Controllers**

- Verify that Server 2 is listed as an RODC.

## Step 2: Demote Server 2

**Server 2 > Server Manager > Manage > Remove Roles and Features**

1. Click Next through the wizard.
2. Uncheck **Active Directory Domain Services (AD DS)**.
3. Select **Remove Features**.
4. Click **Demote this domain controller**.
5. Select **Proceed with removal**.
6. Continue through the wizard.
7. Enter the Local Administrator password.
8. Click **Demote**.
9. Click Close after the process completes.

**Result:** Server 2 restarts automatically.

## Step 3: Verify Workgroup Status

**Server 2 > Login with Local Administrator Account > Server Manager > Local Server**

- Verify that Server 2 is now connected to a Workgroup instead of the domain.

## Step 4: Metadata Cleanup – Active Directory

**Server 1 > Server Manager > Tools > Active Directory Users and Computers > abc.com > Domain Controllers**

1. Refresh the Domain Controllers OU.
2. Verify that Server 2 appears with a down status.
3. Right-click Server 2 and select Delete.
4. Confirm the deletion.

## Step 5: Metadata Cleanup – Sites and Services

**Server 1 > Server Manager > Tools > Active Directory Sites and Services**

1. Expand **Sites**.
2. Expand **Default-First-Site-Name**.
3. Select **Servers**.
4. Right-click Server 2 and select Delete.
5. Confirm the deletion.

---

# ⚙️ Topic 2: RODC Deletion (Metadata Cleanup)

## Step 1: Restore RODC Snapshot & Initial Verification

- Start the previously created RODC snapshot.
- Open Active Directory Users and Computers on Server 1.

**Server 1 > Server Manager > Tools > Active Directory Users and Computers > abc.com > Domain Controllers**

- Verify that Server 2 is listed as an RODC.

**Scenario:** Assume Server 2 has become inaccessible due to a technical issue. In this situation, I need to remove its RODC account and related metadata from Active Directory.

## Step 2: Metadata Cleanup – Active Directory

**Server 1 > Active Directory Users and Computers > abc.com > Domain Controllers**

1. Right-click Server 2.
2. Select Delete.
3. Confirm the deletion.
4. Complete the remaining confirmation prompts.

## Step 3: Metadata Cleanup – Sites and Services

**Server 1 > Server Manager > Tools > Active Directory Sites and Services**

1. Expand **Sites**.
2. Expand **Default-First-Site-Name**.
3. Select **Servers**.
4. Right-click Server 2 and select Delete.
5. Confirm the deletion.

## Step 4: Verify RODC Deletion

**Server 2 > Restart > Login with RODCUser**

Verify the following error message:

`The user database on the server does not have a computer account for this workstation trust relationship.`

This demonstrates that the computer account for Server 2 is no longer available in Active Directory.

---

## 📚 Learning Outcomes

Through these practical exercises, I learned how to:

- Demote a Read-Only Domain Controller.
- Convert a domain controller into a Workgroup server.
- Remove RODC records from Active Directory Users and Computers.
- Clean up server metadata in Active Directory Sites and Services.
- Remove an inaccessible RODC from Active Directory.
- Verify the results of RODC metadata cleanup.

## 🎥 Video Tutorial

**YouTube Video:**  
https://youtu.be/FgVatG3d38o

## 📁 Project Resources

**GitHub Repository:**  
https://github.com/.../Windows-Server-Administration...

**YouTube Playlist:**  
https://youtube.com/playlist?list=PLIEgi_iIRtLI...

## 📝 Conclusion

This lab helped me understand two important RODC management scenarios: normal RODC demotion and metadata cleanup when an RODC becomes inaccessible.

It was another practical step in my Windows Server Administration learning journey, improving my understanding of Active Directory maintenance and domain controller management.

## 🏷️ Tags

#WindowsServer2016 #ActiveDirectory #RODC #ReadOnlyDomainController #MetadataCleanup #SystemAdministration #ITInfrastructure #LearningJourney