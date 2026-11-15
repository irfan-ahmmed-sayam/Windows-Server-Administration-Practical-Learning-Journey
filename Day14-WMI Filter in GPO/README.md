# Day 14 | Windows Server 2016 | WMI Filtering in Group Policy (GPO)

## 📌 Project Overview

In this lab, I practiced **WMI Filtering in Group Policy (GPO)** using Windows Server 2016.

WMI Filtering allows us to apply Group Policy settings based on specific hardware and operating system conditions.

In this practical session, I configured a RAM-based WMI Filter to control the application of a Group Policy.

The main objective was to apply the Group Policy only to systems with **2 GB RAM or less**, while systems with more than 2 GB RAM would not receive the policy.

---

## 🖥️ Lab Environment

| Device | Configuration |
|---|---|
| Server 1 | Domain Controller (DC) |
| Server 2 | 4 GB RAM |
| Client 1 | 2 GB RAM |
| Domain Name | ABC.com |
| Operating System | Windows Server 2016 |


---

## ⚙️ Practical Configuration

### Topic 1: Create a WMI Filter

1. Open Server Manager on Server 1.
2. Navigate to Tools → Group Policy Management.
3. Open WMI Filters.
4. Right-click → New.
5. Set the name: `WMI Filter using RAM`.
6. Click Add to create a new WMI Query.
7. Enter the RAM-based WMI Query.
8. Click OK and save the filter.

**WMI Query:**

```sql
SELECT * FROM Win32_ComputerSystem
WHERE TotalPhysicalMemory <= 2147483648
```

This query matches systems with approximately 2 GB RAM or less.

### Topic 2: Apply WMI Filter to GPO

1. Open Group Policy Management.
2. Select the target GPO.
3. Right-click and open Properties/Scope.
4. Navigate to the WMI Filtering section.
5. Select `WMI Filter using RAM`.
6. Click Yes to confirm.

### Topic 3: Update Group Policy

Run the following command on Server 2:

```powershell
gpupdate /force
```

Run the same command on Client 1:

```powershell
gpupdate /force
```

### Topic 4: Verify WMI Filtering

Check the Group Policy results on both systems.

**Server 2 (4 GB RAM):**
- WMI Filter: Not Matched
- GPO: Not Applied
- Control Panel: Accessible

**Client 1 (2 GB RAM):**
- WMI Filter: Matched
- GPO: Applied
- Control Panel: Blocked


---

## 🎯 Learning Outcome

Through this practical lab, I learned:

- How to create and configure WMI Filters.
- How to write RAM-based WMI Queries.
- How to associate WMI Filters with Group Policy Objects.
- How to apply Group Policy based on hardware resources.
- How to verify GPO application on different systems.

**Final Result:** Successfully configured and tested RAM-based WMI Filtering in Windows Server 2016.

---

## 📚 Learning Journey

This documentation is part of my Windows Server 2016 practical learning journey.

I am documenting each lab with configuration steps, screenshots, and practical results for future reference.

**Day 14: WMI Filtering in Group Policy (GPO)**
