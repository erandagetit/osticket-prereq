 # osticket-prereq<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Account</p>
- Basic knowledge of IIS</p>
- Remote Desktop Access</p>
- osTicket Installation Files</p>
- HeidiSQL</p>

<h2>Installation Steps</h2>

1.) Create a Virtual Machine
<p>
In Microsoft Azure, we will create a VM and add it to a new Resource Group, titled ''osTicket''
</p>
- VM Name: osticket-vm
- Image: Windows 10 Pro, version 22H2-x64 Gen2
- Size: 2 vCPUs, 16 GiB memory
<br />
Navigate to the Virtual Mavhines page and 
select "Create". For this instance we will 
create an Azure Virtual Machine.
<p>

Create a new resource group (if needed),
name the virtual machine, select the region
and the image/operating system.
<p>
Select the preferred cpu size, enter 
adminstrative credentials, check the 
licensing box and review & create the VM.
No changes are needed for management,
disks, or networking sections.

2.) Accessing the Virtual Machine

Retrieve the VM's Public's IP Address and
log using **Remont Desktop** with the
credentials created during the VM setup.

3.) Download and Prepare
Installation Files

- Within the VM, downlaod the
  osTicket-Installation-Files.zip
  and unzip it to your desktop. The folder
  should be named osTicket-
  Installation-Files.

4.) Install IIS and Enable Required
Features

Open Control Panel -> Programs -> Turn
Windows features on or off. Install/enable
IIS with the following features:

- World Wide Web Service ->
  Application Development Features ->
  [X] CGI

5.) Install Required Components

From the osTicket-Installation-Files
folder:

- Install PHP Manager for IIS:
   PHPManagerForIIS_V1.5.0.msi.
- Install Rewrite Module:
   rewrite_amd64_en-US.msi

6.) Setup PHP
  

<p>
<img src="https://i.imgur.com/ROFuXhX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating roles and specifying permissions I can determine whether users can view, edit, or have specific access to sections.
</p>
<br />
