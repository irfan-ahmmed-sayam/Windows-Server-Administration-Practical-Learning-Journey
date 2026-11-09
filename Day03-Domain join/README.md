# Day 03 | Windows Server 2016 | Active Directory Domain Join

## 📌 Project Overview

In this lab, I practiced joining a Windows Server 2016 machine (Server 2) to an existing Active Directory domain named `abc.com`.

First, I verified the domain membership status of Server 2 from Server 1. Then, I tested network connectivity using PowerShell and joined Server 2 to the domain. Finally, I verified the successful domain join through Active Directory Users and Computers.

## 🎯 Objectives

- Verify the initial domain membership status.
- Test network connectivity between servers.
- Join Server 2 to the existing Active Directory domain.
- Authenticate using domain administrator credentials.
- Verify successful domain membership.

## 🖥️ Lab Environment

| Component | Configuration |
|---|---|
| Operating System | Windows Server 2016 |
| Domain Name | abc.com |
| Domain Controller | Server 1 |
| Member Server | Server 2 |
| Server 1 IP Address | 192.168.10.1 |
| Virtualization Platform | VMware |

## ⚙️ Configuration Steps

### Step 1: Verify Server 1

**Server 1 → Server Manager → Tools → Active Directory Users and Computers → abc.com → Computers**

1. Open the Computers container.
2. Verify that Server 2 is not yet domain joined.

### Step 2: Join Server 2 to the Domain

**Server 2 → PowerShell**

1. Test network connectivity:

   `ping 192.168.10.1`

2. Test domain controller name resolution:

   `ping Server1.abc.com`

3. Press `Win + R` and open:

   `sysdm.cpl`

4. Click Change.
5. Select Member of → Domain.
6. Enter the domain name: `abc.com`.
7. Click OK.
8. Enter Administrator credentials.
9. Confirm the changes and close the windows.
10. Select Restart Now.

### Step 3: Verify Domain Join

**Server 1 → Server Manager → Tools → Active Directory Users and Computers → abc.com → Computers**

1. Open the Computers container.
2. Click Refresh.
3. Verify that Server 2 now appears in the domain.

## 📚 Learning Outcomes

Through this practical lab, I gained hands-on experience with:

- Basic network connectivity testing using Ping.
- Domain name resolution.
- Active Directory domain membership.
- Joining a Windows Server to an existing domain.
- Domain administrator authentication.
- Verifying domain membership through Active Directory Users and Computers.

## 🎥 Video Tutorial

[Watch on YouTube – Day 03: Active Directory Domain Join](https://youtu.be/DfK9v-r3_Ws)

## 📁 Project Resources

- **GitHub Repository:** [Windows Server Administration](https://github.com/.../Windows-Server-Administration...)
- **YouTube Playlist:** [Windows Server Learning Journey](https://youtube.com/playlist?list=PLIEgi_iIRtLI...)

## 🚀 Conclusion

This practical lab helped me understand the process of joining a Windows Server machine to an existing Active Directory domain.

I also practiced basic network connectivity testing, domain authentication, and domain membership verification.

Another important step in my Windows Server Administration learning journey.

---

**#WindowsServer2016 #ActiveDirectory #DomainJoin #WindowsServer #SystemAdministration #ITInfrastructure #LearningJourney #HandsOnLearning**