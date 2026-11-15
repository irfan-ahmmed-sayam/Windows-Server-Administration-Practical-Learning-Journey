# Day 13 | Windows Server 2016 | GPO Backup, Restore & Import Settings

## 📌 Overview

In this practical lab, I worked with Group Policy Management (GPMC) in Windows Server 2016.

The main objective was to practice three important GPO management operations:

1. **GPO Backup** – Back up all existing Group Policy Objects.
2. **GPO Restore** – Restore a deleted GPO from its backup.
3. **GPO Import Settings** – Import settings from an existing GPO into a newly created GPO.

These tasks helped me understand how to protect, recover, and reuse Group Policy configurations.

---

## 📺 Learning Resources

- **YouTube Video:** [Day 13 – GPO Backup, Restore & Import](https://youtu.be/LOOw2WiWTuw)
- **YouTube Playlist:** [Windows Server Administration Practical Learning Journey](https://youtube.com/playlist?list=PLIEgi_iIRtLI&si=_ZNz737lzJe94scf)
- **GitHub Repository:** [Windows Server Administration Practical Learning Journey](https://github.com/irfan-ahmmed-sayam/Windows-Server-Administration-Practical-Learning-Journey)

---

## ⚙️ Lab Environment

- **Operating System:** Windows Server 2016
- **Domain Name:** ABC.com
- **Management Tool:** Group Policy Management
- **Server:** Server 1

### Existing Group Policy Objects

There were five GPOs in the domain:

**Custom GPOs:**
- Block Control Panel
- CMD Block
- Remove Task Manager

**Default GPOs:**
- Default Domain Policy
- Default Domain Controllers Policy

---

## 🛠️ Configuration Steps

### Topic 1: GPO Backup

**Objective:** Create a backup of all five existing GPOs.

**Steps:**

1. Open Server Manager.
2. Go to Tools → Group Policy Management.
3. Navigate to Forest → Domains → ABC.com → Group Policy Objects.
4. Right-click Group Policy Objects.
5. Select **Back Up All**.
6. Browse and select the backup destination folder.
7. Click Backup → OK.
8. Open File Explorer and verify the backup files.

**Result:** All five existing GPOs were successfully backed up.

---

### Topic 2: GPO Restore

**Objective:** Delete and restore the CMD Block GPO using its backup.

**Steps:**

1. Navigate to Group Policy Objects.
2. Right-click **CMD Block** → Delete.
3. Confirm the deletion.
4. Right-click Group Policy Objects → Manage Backups.
5. Locate the CMD Block backup.
6. Select the backup and click Restore.
7. Confirm with Yes → OK.
8. Click Close.
9. Verify that CMD Block is available again under Group Policy Objects.

**Result:** The deleted CMD Block GPO was successfully restored from its backup.

---

### Topic 3: Import GPO Settings

**Objective:** Import settings from the existing Remote Task Manager GPO into a new GPO.

**Steps:**

1. Open Group Policy Management.
2. Review the existing **Remote Task Manager** GPO settings.
3. Navigate to Group Policy Objects.
4. Right-click → New.
5. Create a new GPO named **Import GPO**.
6. Select Import GPO and check its Settings section.
7. Right-click Import GPO → Import Settings.
8. Click Next → Next.
9. Browse and select the GPO backup location.
10. Select **Remote Task Manager** from the backup.
11. Click Next → Next → Finish.
12. Click OK.
13. Verify the imported settings inside Import GPO.

**Result:** The settings from Remote Task Manager were successfully imported into the new Import GPO.

---

## 📚 Important Concepts

| Operation | Purpose |
|---|---|
| GPO Backup | Saves a backup of an existing GPO. |
| GPO Restore | Recovers a GPO from its backup. |
| GPO Import | Copies policy settings from a backup into another GPO. |

**Important Difference:**

- Backup and Restore are used to protect and recover GPOs.
- Import Settings allows us to reuse existing policy settings in another GPO.
- Import Settings does not simply restore the original GPO; it transfers its policy settings into the destination GPO.

---

## 📸 Practical Documentation

This repository contains practical screenshots documenting the configuration process.

The screenshots cover:

- GPO Backup process
- Backup folder verification
- CMD Block GPO deletion
- GPO Restore process
- Creating a new Import GPO
- Importing Remote Task Manager settings
- Final settings verification

---

## 🎯 Learning Outcomes

Through this practical lab, I learned how to:

- Back up multiple Group Policy Objects.
- Restore a deleted Group Policy Object.
- Create a new GPO.
- Import settings from an existing GPO.
- Understand the differences between Backup, Restore, and Import operations.
- Manage Group Policy configurations using Group Policy Management.

---



**Note:** This documentation is part of my Windows Server Administration Practical Learning Journey. I am documenting my hands-on lab configurations, screenshots, and learning experiences for future reference.

#WindowsServer2016 #GPO #GroupPolicyManagement #GPOBackup #GPORestore #ImportGPO #ActiveDirectory #LearningJourney
