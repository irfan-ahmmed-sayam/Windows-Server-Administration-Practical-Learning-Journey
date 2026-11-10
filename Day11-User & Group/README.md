# Day 11 \| Windows Server 2016 \| Active Directory Users & Groups Management

This documentation covers my hands-on practice with **Active Directory
user creation, Organizational Units (OU), security groups, and group
membership management** in Windows Server 2016.

The repository includes theoretical notes and approximately 40--50
annotated screenshots. The screenshots highlight the relevant options,
menus, and configuration areas used throughout the lab.

## 🎥 YouTube Video

[Watch the Day 11 practical lab](https://youtu.be/ABTRMXeA7_Y)

## 📚 Repository Resources

-   **Practical screenshots:** Step-by-step screenshots with important
    options and configuration areas highlighted.
-   **Theoretical notes:** Digital notes covering the related Active
    Directory concepts.
-   **Lab documentation:** Practical workflow and verification steps.

## 🧪 Lab Overview

### 1. Create a Domain User and Sign In to Client 1

-   Open **Server Manager → Tools → Active Directory Users and
    Computers** on Server 1.
-   Navigate to **ABC.com → Users**.
-   Create a new user with the logon name `user1`.
-   Set a password and enable **Password never expires**.
-   Sign in to Client 1 using `user1@abc.com`.

### 2. Create an Organizational Unit and Users

-   Create an Organizational Unit named **IT** under the `ABC.com`
    domain.
-   Inside the IT OU, create these four users:
    -   IT Admin 1
    -   IT Admin 2
    -   IT User 1
    -   IT User 2
-   Set a password for each account and enable **Password never
    expires**.

### 3. Create Global Security Groups

Inside the IT OU, create these groups:

  Group name   Group scope   Group type
  ------------ ------------- ------------
  IT Admin     Global        Security
  IT User      Global        Security

### 4. Add Users to Groups --- Method 1

-   Open **IT Admin → Properties → Members → Add**.
-   Enter `IT`, select **Check Names**, and choose **IT Admin 1** and
    **IT Admin 2**.
-   Apply the changes.
-   Verify membership from **IT Admin 1 → Properties → Member Of**.

### 5. Add Users to Groups --- Method 2

-   Open **IT User 1 → Properties → Member Of → Add**.
-   Enter `IT User`, select **Check Names**, and choose the IT User
    group.
-   Apply the changes.
-   Verify the membership from the user's **Member Of** tab and the
    group's **Members** tab.

### 6. Explore Active Directory Administrative Center (ADAC)

-   Open **Server Manager → Tools → Active Directory Administrative
    Center**.
-   Navigate to **ABC.com (Local) → IT → New → User**.
-   Create a user with the logon name `user11` and domain `abc.com`.
-   Explore the **Organization** section and its additional
    user-information fields.

## 🗂️ Lab Environment

-   **Server:** Windows Server 2016
-   **Domain:** `ABC.com`
-   **Client:** Client 1
-   **Active Directory tools:** Active Directory Users and Computers
    (ADUC), Active Directory Administrative Center (ADAC)

## 🎯 What I Practiced

-   Creating a domain user in Active Directory.
-   Signing in to a client computer with a domain account.
-   Creating an Organizational Unit (OU).
-   Creating and managing multiple user accounts.
-   Creating Global Security Groups.
-   Adding users to groups using two different methods.
-   Checking group membership using **Members** and **Member Of**.
-   Exploring additional user attributes in ADAC.

## 📝 Notes

This is part of my ongoing **Windows Server Administration Practical
Learning Journey**. I am documenting my own lab practice for learning,
revision, and future reference.

The annotated screenshots and theoretical notes are included in this
repository to make it easier to follow the configuration process and
review the concepts.

------------------------------------------------------------------------

**Learning by doing \| Documenting every step**
