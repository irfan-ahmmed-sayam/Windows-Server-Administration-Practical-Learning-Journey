# Day 12 \| Windows Server 2016 \| GPO Linking, Block Inheritance & Enforcement

## Overview

In this practical lab, I worked with **Group Policy Management** in
Windows Server 2016. I created and linked Group Policy Objects (GPOs),
applied policies at the domain and Organizational Unit (OU) levels, and
tested how **Block Inheritance** and **Enforced** affect Group Policy
processing.

The lab uses the `ABC.com` domain with one server and two domain-joined
clients.

## Lab Environment

  Device     Role
  ---------- -----------------------------------------------
  Server 1   Domain Controller and Group Policy Management
  Client 1   Domain client logged in as `IT User 1`
  Client 2   Domain client logged in as `HR User 1`
  Domain     `ABC.com`

> **Starting point:** Server 1, Client 1, and Client 2 were started from
> their Domain Joined snapshots.

## OU and User Configuration

Under the `ABC.com` domain, I created two Organizational Units:

-   `IT`
    -   `IT User 1`
-   `HR`
    -   `HR User 1`

I then signed in to:

-   **Client 1** using `IT User 1`
-   **Client 2** using `HR User 1`

## GPOs Created

I created the following three Group Policy Objects under **Group Policy
Objects**:

1.  `Block Control Panel`
2.  `CMD Block`
3.  `Remove Task Manager`

The domain already contained its default policies:

-   `Default Domain Policy`
-   `Default Domain Controllers Policy`

## Practical Configuration

### Topic 1: Create the OUs and Users

1.  Open **Server Manager** on Server 1.
2.  Go to **Tools → Active Directory Users and Computers**.
3.  Open the `ABC.com` domain.
4.  Create the `IT` and `HR` Organizational Units.
5.  Create `IT User 1` inside the IT OU.
6.  Create `HR User 1` inside the HR OU.
7.  Sign in to Client 1 as `IT User 1` and Client 2 as `HR User 1`.

### Topic 2: Create the GPOs

1.  On Server 1, open **Server Manager → Tools → Group Policy
    Management**.
2.  Expand `Forest → Domains → ABC.com`.
3.  Open **Group Policy Objects**.
4.  Create these three GPOs:
    -   `Block Control Panel`
    -   `CMD Block`
    -   `Remove Task Manager`

### Topic 3: Link CMD Block to the HR OU

1.  In Group Policy Management, right-click the **HR** OU.

2.  Select **Link an Existing GPO**.

3.  Choose `CMD Block` and click **OK**.

4.  On Client 2, sign in as `HR User 1`.

5.  Run:

    ``` cmd
    gpupdate /force
    ```

6.  Try to open Command Prompt. Verify that Windows displays the
    administrator restriction message.

**Result:** The CMD Block policy is linked to the HR OU and applies to
the HR user in this lab.

### Topic 4: Link Block Control Panel to the Domain

1.  In Group Policy Management, right-click the `ABC.com` domain.

2.  Select **Link an Existing GPO**.

3.  Choose `Block Control Panel` and click **OK**.

4.  On Client 1, run:

    ``` cmd
    gpupdate /force
    ```

5.  Try to open Control Panel and verify that access is restricted.

6.  Repeat the verification on Client 2.

**Result:** The Block Control Panel GPO is linked at the domain level,
so it applies to users in both the IT and HR OUs in this lab.

### Topic 5: Link Remove Task Manager to the Domain

1.  Return to Group Policy Management on Server 1.
2.  Right-click the `ABC.com` domain.
3.  Select **Link an Existing GPO**.
4.  Choose `Remove Task Manager` and click **OK**.

### Topic 6: Configure Block Inheritance on the IT OU

1.  In Group Policy Management, right-click the **IT** OU.
2.  Select **Block Inheritance**.

**What this does:** Block Inheritance prevents ordinary GPO links
inherited from parent containers, including the domain, from applying to
the IT OU. It does not block GPOs marked as **Enforced**.

### Topic 7: Configure Enforced GPOs

1.  Under the `ABC.com` domain, locate the linked
    `Default Domain Policy`.
2.  Right-click it and enable **Enforced**.
3.  Locate the linked `Remove Task Manager` GPO.
4.  Right-click it and enable **Enforced**.

**What this does:** Enforced GPO links continue to apply to child OUs
even when Block Inheritance is enabled on those OUs.

## Final Verification

Update Group Policy and review the applied policies on both clients.

### Client 1 --- IT User 1

Run:

``` cmd
gpupdate /force
gpresult /r
```

Check the **Applied Group Policy Objects** section.

Expected lab result:

-   `Default Domain Policy` --- enforced
-   `Remove Task Manager` --- enforced
-   `Block Control Panel` --- not applied to the IT OU because Block
    Inheritance is enabled and this GPO is not enforced

### Client 2 --- HR User 1

Run:

``` cmd
gpupdate /force
gpresult /r
```

Check the **Applied Group Policy Objects** section.

Expected lab result:

-   `Block Control Panel` --- linked at the domain level
-   `Remove Task Manager` --- linked at the domain level and enforced
-   `CMD Block` --- linked directly to the HR OU

## Key Learning Points

-   Creating Organizational Units and domain users
-   Creating and linking Group Policy Objects
-   Applying a GPO to a specific OU
-   Applying a GPO at the domain level
-   Understanding GPO inheritance
-   Configuring Block Inheritance
-   Configuring Enforced GPO links
-   Updating and verifying Group Policy with `gpupdate /force` and
    `gpresult /r`

## Screenshots and Practical Documentation

Screenshots showing the configuration process and verification results
are included with this GitHub project.

Add or update the image paths below to match the actual screenshot
filenames and folder names in this repository. For example:

``` md
![GPO configuration screenshot](Screenshots/Day-12/01-gpo-configuration.png)
```

Suggested screenshot organization:

``` text
Screenshots/
└── Day-12/
    ├── 01-ou-and-user-creation.png
    ├── 02-gpo-creation.png
    ├── 03-cmd-block-linked-to-hr.png
    ├── 04-cmd-block-client-verification.png
    ├── 05-block-control-panel-domain-link.png
    ├── 06-control-panel-client-verification.png
    ├── 07-remove-task-manager-domain-link.png
    ├── 08-block-inheritance-it-ou.png
    ├── 09-default-domain-policy-enforced.png
    ├── 10-remove-task-manager-enforced.png
    ├── 11-client-1-gpresult.png
    └── 12-client-2-gpresult.png
```

## Conclusion

This lab helped me understand how GPO links, inheritance, Block
Inheritance, and Enforced settings affect policy application across
domain and OU structures in Windows Server 2016.

This is another practical step in my **Windows Server Administration
Practical Learning Journey**.

------------------------------------------------------------------------

**Note:** This repository contains practical lab documentation and
screenshots from my own learning and configuration practice.
