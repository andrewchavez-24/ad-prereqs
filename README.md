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

- Windows Server 2022, 2vCPUs, 8GM RAM
- Windows 10 Pro (22H2), 2vCPUs, 8GB RAM

<h2>High-Level Deployment and Configuration Steps</h2>

- Create a Virtual Network
- Setup Domain Controller in Azure
- Setup Client-1 in Azure
- Join Client-1 to Domain

<h2>Deployment and Configuration Steps</h2>

<h3>Create a Virtual Network</h3>
<p>
Create a Resource Group
</p>
<p>
<img src="https://github.com/user-attachments/assets/19ef657e-5729-4777-a5d2-516c71506828" height="80%" width="80%"/>
</p>

<br>
<p>
Create a Virtual Network and Subnet
</p>
<p>
<img src="https://github.com/user-attachments/assets/e8bfb662-2043-4073-a8b6-4924281d909f" height="80%" width="80%"/>
</p>

<br>
<h3>Set up Domain Controller in Azure</h3>
<p>
Create the Domain Controller VM (Windows Server 2022) named “DC-1”
</p>
<p>
<img src="https://github.com/user-attachments/assets/7733a732-4a22-44f4-9d47-ed9b1e0ea837" height="80%" width="80%"/>
</p>

<br>
<h3>Set up Client-1 in Azure</h3>
<p>
Create the Client VM (Windows 10) named “Client-1”
</p>
<p>
<img src="https://github.com/user-attachments/assets/bf5288e4-919f-4a82-96cb-b86269ec944e" height="80%" width="80%"/>
</p>

<br>
<h3>Join Client-1 to the Domain Controller</h3>
<p>
After VM is created, set Domain Controller’s NIC Private IP address to be static
</p>
<p>
<img src="https://github.com/user-attachments/assets/1b2c9237-32ea-4c5e-bc0b-bb04e6241cf3" height="80%" width="80%"/>
</p>

<br>
<p>
Log into the VM and disable the Windows Firewall (for testing connectivity)
</p>
<p>
<img src="https://github.com/user-attachments/assets/c3502fc0-39ea-4149-bbf2-c066bde1d19e" height="80%" width="80%"/>
</p>

<br>
<p>
After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address
</p>
<p>
<img src="https://github.com/user-attachments/assets/ebba5da2-cfcd-46a6-bdd5-b9a31c4449a8" height="80%" width="80%"/>
</p>

<br>
<p>
From the Azure Portal, restart Client-1
</p>

<br />
<h3>Verify that Client-1 is joined to the Domain</h3>
<p>
Login to Client-1
</p>

<br />
<p>
Attempt to ping DC-1’s private IP address
</p>
<p>
<img src="https://github.com/user-attachments/assets/398472cd-bfb2-4206-9283-c631add9aaf2" height="80%" width="80%"/>
</p>

<br>
<p>
From Client-1, open PowerShell and run ipconfig /all
The output for the DNS settings should show DC-1’s private IP Address
</p>
<p>
<img src="https://github.com/user-attachments/assets/a4e1bb03-a9f7-4292-a6b3-45254af73bef" height="80%" width="80%"/>
</p>

<h2>Active Directory Infrastructure is Now Prepared! </h2>

<b>We've successfully created two VMs (Virtual Machines), one running Windows Server, to act as a Domain Controller. The other VM joined as a client, running Windows 10.</b>
<br />
<br />
</p>
