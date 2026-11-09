# Day 10 \| Windows Server 2016 \| Group Policy Object (GPO) & Organizational Unit (OU)

## Overview

In this lab, I practiced creating and configuring Group Policy Objects
(GPOs) to restrict access to Control Panel and PC Settings. I also
explored different methods of applying Group Policy updates.

Additionally, I practiced creating Organizational Units (OUs), creating
nested OUs, and deleting an OU after disabling accidental deletion
protection.

## Resources

-   **YouTube Video:** [Add Day 10 Video Link](#)
-   **GitHub Repository:** [Windows Server Administration -- Practical
    Learning
    Journey](https://github.com/irfan-ahmmed-sayam/Windows-Server-Administration-Practical-Learning-Journey)
-   **YouTube Playlist:** [Windows Server Administration
    Playlist](https://youtube.com/playlist?list=PLIEgi_iIRtLI&si=_ZNz737lzJe94scf)

------------------------------------------------------------------------

## Topic 1: Group Policy Object (GPO) -- Block Control Panel

### Step 1: Create a New GPO

1.  Open **Server Manager** on Server 1.
2.  Go to **Tools → Group Policy Management**.
3.  Navigate to **Forest → ABC.com → Domains → ABC.com**.
4.  Right-click **ABC.com** and select **Create a GPO in this domain,
    and Link it here**.
5.  Enter the GPO name: `Block Control Panel`.
6.  Click **OK**.

### Step 2: Configure GPO Settings

1.  Right-click **Block Control Panel** and select **Edit**.

2.  Navigate to:

    `User Configuration → Policies → Administrative Templates → Control Panel`

3.  Open **Prohibit access to Control Panel and PC Settings**.

4.  Select **Enabled → Apply → OK**.

### Step 3: Verify Before Applying the GPO

1.  On Server 1, try to open Control Panel.
2.  Verify that it is still accessible because the Group Policy has not
    yet been refreshed.

### Step 4: Apply GPO -- Method 1 (GPUpdate /force)

1.  Open PowerShell on Server 1.

2.  Run:

    ``` powershell
    gpupdate /force
    ```

3.  Try to open Control Panel again.

4.  Verify that access is now restricted.

### Step 5: Apply GPO -- Method 2 (Restart)

1.  Restart Server 1.
2.  After restarting, try to open Control Panel.
3.  Verify that the restriction message appears.

### Step 6: Apply GPO -- Method 3 (Sign Out & Sign In)

1.  Sign out from Client 1.
2.  Sign in again.
3.  Try to open Control Panel.
4.  Verify that the same restriction message appears.

------------------------------------------------------------------------

## Topic 2: Organizational Unit (OU) -- Creation & Deletion

### Step 1: Create a New Organizational Unit

1.  On Server 1, open **Server Manager → Tools → Active Directory Users
    and Computers**.
2.  Expand **ABC.com**.
3.  Right-click **ABC.com → New → Organizational Unit**.
4.  Enter the OU name: `IT`.
5.  Click **OK**.

### Step 2: Create a Sub-Organizational Unit

1.  Right-click the **IT** OU.
2.  Select **New → Organizational Unit**.
3.  Enter the OU name: `IT Main`.
4.  Click **OK**.

### Step 3: Create Another Organizational Unit

1.  Right-click **ABC.com**.
2.  Select **New → Organizational Unit**.
3.  Enter the OU name: `Sales`.
4.  Click **OK**.

The domain now contains two main OUs: **IT** and **Sales**. The **IT**
OU contains a nested OU named **IT Main**.

### Step 4: Try to Delete an OU

1.  Right-click **IT Main** and select **Delete**.
2.  Confirm the deletion attempt.
3.  Observe the error indicating that there are insufficient privileges
    to delete the object.

### Step 5: Disable Accidental Deletion Protection

1.  In Active Directory Users and Computers, select **View → Advanced
    Features**.
2.  Right-click **IT Main** and select **Properties**.
3.  Open the **Object** tab.
4.  Uncheck **Protect object from accidental deletion**.
5.  Click **Apply → OK**.

### Step 6: Delete the Organizational Unit

1.  Right-click **IT Main**.
2.  Select **Delete** and confirm.
3.  Verify that the **IT Main** OU has been deleted successfully.

------------------------------------------------------------------------

## What I Practiced

-   Creating and linking a Group Policy Object.
-   Configuring a policy to block Control Panel and PC Settings.
-   Applying Group Policy updates using `gpupdate /force`, restarting,
    and signing out/in.
-   Creating Organizational Units and nested OUs in Active Directory.
-   Understanding accidental deletion protection.
-   Disabling deletion protection and deleting an OU.

## Learning Journey

Another practical step in my Windows Server Administration learning
journey, focusing on Group Policy management, policy enforcement, and
Active Directory Organizational Unit management.

## Tags

`Windows Server 2016` `Group Policy` `GPO` `Active Directory`
`Organizational Unit` `OU` `System Administration` `IT Infrastructure`
`Windows Server Administration` `Learning Journey`
