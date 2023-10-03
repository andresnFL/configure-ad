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

- Setting up resources 
- Ensure connectivity
- Installing Active Directory
- Create Admin and User accounts
- Connecting Client to Domain
- Testing Users with remote desktop



<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://imgur.com/VCsOVar.png" height="40%" width="40%" alt="Disk Sanitization Steps"/> 
</p>
<p>
First off, Create a virtual machine named DomainController, use Windows Server 2022 for the VM. After creation, venture into your newly created resource within Azure > Then Networking > and finally IP Configuration (IpConfig). Access the private IP Address and change status of IP Address from Dynamic to Static to allow client to join domain. (PIC). Create a second VM (Client-1), using the same resource group as your domain controller. To ensure both are in the same Vnet, use Network Watcher to verify. 
</p>
<br />

<p>
<img src="https://imgur.com/yut7ozG.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><img src="https://imgur.com/wzY8MuF.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log into Client-1 through remote desktop and ping DC-1's private IP with a perpetual ping command (ping -t <ip address>). On the domain controller's firewall. enable ICMPv4 (PIC 1). Go back to Client-1 to see if the ping succeeds. (PIC 2)
</p>
<br />

<p>
<img src="https://imgur.com/uBhMk18.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><img src="https://imgur.com/byw4KZp.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enter Add Roles and Features within DomainController. Follow the steps and Install Active Directory Domain Services (PIC 1). Click on the exclamation point in the dashboard and set up a new "Forest" named Mydomain.com (Take note). Restart the Remote connection and log back into under: Mydomain.com\labuser (PIC 2)

</p>
<br />

<p>
<img src="https://imgur.com/4uAYWWr.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><img src="https://imgur.com/AGh6O1o.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Active Directory Users and Computers, create an organizational unit called "_EMPLOYEES". Create another OU called "_ADMIN". (PIC 1) Then create a new employee named "Jane Doe" with the username of "jane_admin". Add Jane to the Domain Admins security group.(PIC 2) Restart and log in as Mydomain.com\jane_admin. This will be your admin user from now on. 
</p>
<br />

<p>
<img src="https://imgur.com/2dHIC5v.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
From Microsoft Azure, change Client-1's DNS settings to the DomainController's Private IP Address. Restart Client-1 within Azure. (PIC 1)

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

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
