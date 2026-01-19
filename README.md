

<p align="center">
  <img src="https://github.com/user-attachments/assets/ccf710f0-3658-494d-aca6-fcaea462f1b5" alt="Network File Shares and Permissions banner" width="900" />
</p>

# Network File Shares and Permissions
This tutorial outlines how to configure file shares and permissions in Active Directory.

## Environments and Technologies Used
- Microsoft Azure (Virtual Machines / Compute)
- Remote Desktop Protocol (RDP)
- Active Directory Domain Services (AD DS)
- Windows File Sharing

## Operating Systems Used
- Windows Server 2022 Datacenter (Domain Controller – DC-1)
- Windows 10 Pro (Client – Client-1)

## List of Prerequisites
- Make sure both **DC-1** and **Client-1** are turned on in the Azure Portal.
- Log into DC-1 using the domain administrator account: **`mydomain.com\jane_admin`**.
- Log into Client-1 using a regular domain user account: **`mydomain\<someuser>`**.
- This lab assumes you already have **Active Directory** deployed and working from previous labs.

## Create File Shares with Permissions on DC-1
- Log into **DC-1** as **`mydomain.com\jane_admin`**.
- On the **C:\** drive, create four folders:
  - **read-access**
  - **write-access**
  - **no-access**
  - **accounting**
- Right-click each folder → **Properties** → **Sharing** → **Advanced Sharing**, then configure:
  - **read-access** → Group: **Domain Users**, Permission: **Read**
  - **write-access** → Group: **Domain Users**, Permission: **Read/Write**
  - **no-access** → Group: **Domain Admins**, Permission: **Read/Write**
  - **accounting** → leave untouched for now

<p align="center">
  <img src="https://github.com/user-attachments/assets/151303ee-92b0-4588-9c95-ad1425f16c90" alt="Create folder shares" width="800" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/0c180761-7bab-4a5d-ba23-925691f25bab" alt="Share permissions" width="800" />
</p>

## Test File Share Access from Client-1
- Log into Client-1 as a normal domain user (**`mydomain\<someuser>`**).
- Open the Run dialog (Win + R) and type **`\\dc-1`**.
- Try accessing each folder:
  - You should be able to open **read-access** but only read files.
  - You should be able to open and create files in **write-access**.
  - You should not be able to access **no-access**.
- Confirm the observed behavior matches the permissions you set on DC-1.

<p align="center">
  <img src="https://github.com/user-attachments/assets/c2743b23-e35b-4039-87d4-fe584520ba22" alt="Access shares from Client-1" width="800" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/163af068-08d5-4dc2-bafe-b2fcabcf8c74" alt="Permissions result" width="800" />
</p>

## Create an ACCOUNTANTS Security Group and Assign Permissions
- Back on DC-1, open **Active Directory Users and Computers (ADUC)**.
- Create a new security group called **ACCOUNTANTS**.
- Return to the **accounting** folder properties and set:
  - Group: **ACCOUNTANTS**
  - Permissions: **Read/Write**
- Log back into Client-1 as **`<someuser>`** and try to access the **accounting** share.
- It should fail because the user is not yet in the **ACCOUNTANTS** group.

  <img width="975" height="703" alt="image" src="https://github.com/user-attachments/assets/5632bc0b-362b-4b37-9b05-86552964cf70" />

  <img width="975" height="722" alt="image" src="https://github.com/user-attachments/assets/b5833d99-6c7a-4648-9ea6-95b5f424a1b0" />

  <img width="975" height="501" alt="image" src="https://github.com/user-attachments/assets/01f6e98a-2307-4205-8ea7-77dd1ddc5197" />



   ## Add User to ACCOUNTANTS Group and Retest Access

- While logged into <b>DC-1</b>, add <b>`<someuser>`</b> to the <b>ACCOUNTANTS</b> group in <b>ADUC</b>.
- Sign out of <b>Client-1</b> and sign back in as <b>`<someuser>`</b>.
- Try to access the <b>accounting</b> share again.
- This time, access should succeed because the user is now a group member.

  <img width="623" height="727" alt="image" src="https://github.com/user-attachments/assets/88ab7d1d-35b2-4811-9588-6ef40368b6ac" />

  <img width="434" height="123" alt="image" src="https://github.com/user-attachments/assets/b7af6b97-eee8-4fec-883b-34cf957a38d5" />

  <img width="975" height="270" alt="image" src="https://github.com/user-attachments/assets/9075e4e9-df5a-46e1-8e0d-a25fbe4525d1" />



  ## Save or Delete VMs

- After testing is complete, you can either keep the VMs available for practice or delete them to save resources.
- If you intend to continue future labs, it’s recommended to <b>stop</b> rather than <b>delete</b> the VMs.

  <img width="975" height="187" alt="image" src="https://github.com/user-attachments/assets/425a1197-e787-4a60-a5f8-50daba350f81" />







  






