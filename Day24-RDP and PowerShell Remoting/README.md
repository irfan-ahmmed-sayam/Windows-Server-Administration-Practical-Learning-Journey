# Day 24 – Remote Access Using RDP and PowerShell Remoting

This lab covers two methods of remotely accessing and managing systems in a Windows Server environment:

1. **Remote Desktop Protocol (RDP)**
2. **PowerShell Remoting**

The practical demonstration uses **Server 1** to remotely access **Server 2** through RDP and to remotely access **CLI 1** through PowerShell Remoting.

## Lab Overview

| System | Role |
|---|---|
| Server 1 | Main server used to initiate remote connections |
| Server 2 | Remote system accessed through RDP |
| CLI 1 | Command-line system accessed through PowerShell Remoting |

## 1. Remote Access Using RDP

RDP provides graphical remote access to another Windows system.

### Steps Performed

1. Check network connectivity between Server 1 and Server 2.
2. On the target system (Server 2), open `System.cpl`.
3. Go to the Remote settings and enable Remote Desktop access.
4. From Server 1, connect to Server 2 using its IP address or computer name.
5. Sign in with the appropriate credentials.

## 2. Remote Access Using PowerShell Remoting

PowerShell Remoting allows remote administration through PowerShell commands.

### Steps Performed

1. Check network connectivity between Server 1 and CLI 1.
2. Enable the required PowerShell Remoting configuration on CLI 1.
3. From Server 1, connect to CLI 1 using PowerShell Remoting.

### Two PowerShell Remoting Methods

**Method 1 – Direct remote access**

Use `Enter-PSSession` to start an interactive remote session directly, without manually creating a separate session first.

```powershell
Enter-PSSession -ComputerName <CLI-1-Name>
```

**Method 2 – Create a session first**

Create a remote session with `New-PSSession`, then enter that session using `Enter-PSSession`.

```powershell
$Session = New-PSSession -ComputerName <CLI-1-Name>
Enter-PSSession -Session $Session
```

## RDP vs PowerShell Remoting

The infographic below provides a visual overview of the two remote-access methods used in this lab.

![RDP vs PowerShell Remoting Infographic](RDP%20vs%20PowerShell%20Remoting%20Infographic.png)

> **Note:** Keep the image file in the same folder as this `README.md` file, using the exact filename `RDP vs PowerShell Remoting Infographic.png`, so it displays correctly on GitHub.

## YouTube Video Reference

Watch the complete practical demonstration:

**[Day 24 – Remote Access Using RDP & PowerShell Remoting](https://youtu.be/qwYF0iZC1CI)**

Replace `https://youtu.be/qwYF0iZC1CI` with the actual YouTube video URL.

## Learning Notes

This lab is part of my ongoing Windows Server and IT infrastructure learning journey. I practiced remote access through both a graphical interface (RDP) and a command-line interface (PowerShell Remoting), and documented the configuration steps for future reference.

---

**Topics:** Windows Server · RDP · PowerShell Remoting · Remote Administration · `System.cpl` · `Enter-PSSession` · `New-PSSession`
