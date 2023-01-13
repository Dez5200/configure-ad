# configure-ad
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup Resources in Azure
- Install Active Directory and Create an Admin and Normal User Account in AD
- Setup Remote Desktop for non-administrative users on Client-1 
- Put both VM's on the Same Network and Install Script on Powershell

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://https://i.imgur.com/1HoOxov.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>

</p>
<br />

<p>
<img src="https://i.imgur.com/1HoOxov.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>The purpose of Active Directory is too manage thousands of users on the same premises.The first step to configuring and installing Active Directory is too create and install 2 VM's and make one of them the Domain Controller. The Domain Controller is just a computer that has Active Directory installed on it. When installing the VM's, I would seperate the VM's by name and make one DC-1 and the Client-1 so you know which is the Domain Controller. Also check the virtual network between the Two VM's. 
</p>
<br />

<p>
<img src="https://i.imgur.com/KzMmIjP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login to DC-1 and install Active Directory Domain Services and Promote as a DC. Restart and then log back into DC-1 as user: mydomain.com\labuser.Create an Admin and Normal User Account in AD. In Active Directory Users and Computers, create an Organizational Unit (OU) called “_EMPLOYEES”. Create a new OU named “_ADMINS” and
Create a new employee with any name you want too and add the name to "Domain Admins" and Log out/close the Remote Desktop connection to DC and log back in as the new name you decided to use and that will be your admin account from now on.
</p>
<br />

<img src="https://i.imgur.com/NwALyjl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Login to DC-1 as the Admin and Open PowerShell ISE  as an administrator. Create a new File and paste the contents of a script into it and run the script and observe the accounts being created. With the accounts being created, it gives thousands of different users on the network access to these computers.
