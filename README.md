<p align="center">
<img width="1155" height="642" alt="image" src="https://github.com/user-attachments/assets/ccf710f0-3658-494d-aca6-fcaea462f1b5" />
>
</p>

<h1>Network File Shares and Permissions</h1>
This tutorial outlines how to configure file shares and permissions in active directory<br />



<h2>Environments and Technologies Used</h2>\

- Microsoft Azure (Virtual Machines / Compute)
- Remote Desktop Protocol (RDP)
- Active Directory Domain Services (AD DS)
- Windows File Sharing


<h2>Operating Systems Used </h2>

- Windows Server 2022 Datacenter (Domain Controller – DC-1)
- Windows 10 Pro (Client – Client-1)


<h2>List of Prerequisites</h2>

- Make sure both <b>DC-1</b> and <b>Client-1</b> are turned on in the Azure Portal.
- Log into <b>DC-1</b> using the domain administrator account: <b>mydomain.com\jane_admin</b>.
- Log into <b>Client-1</b> using a regular domain user account: <b>mydomain\<someuser></b>.
- This lab assumes you already have <b>Active Directory</b> deployed and working from previous labs.


<h2>Create File Shares with Permissions on DC-1</h2>


- Log into <b>DC-1</b> as <b>mydomain.com\jane_admin</b>.
- On the <b>C:\</b> drive, create four folders:
  - <b>read-access</b>
  - <b>write-access</b>
  - <b>no-access</b>
  - <b>accounting</b>
- Right-click each folder → <b>Properties</b> → <b>Sharing</b> → <b>Advanced Sharing</b>, then configure:

  - <b>read-access</b> → Group: <b>Domain Users</b>, Permission: <b>Read</b>
  - <b>write-access</b> → Group: <b>Domain Users</b>, Permission: <b>Read/Write</b>
  - <b>no-access</b> → Group: <b>Domain Admins</b>, Permission: <b>Read/Write</b>
  - <b>accounting</b> → leave untouched for now


















<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
