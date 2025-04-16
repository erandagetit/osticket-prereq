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

- Navigate to the C: drive and create the
  directory C:\PHP
- Unzip PHP 7.3.8 (php-7.3.8-nts-
  Win32-VC15-x86.zip) into the C:\PHP
  folder.
- Install VC_redist.x86.exe.

7.) Install MySQL

- From the osTicket-Installation-
  Files folder, install MySQL 5.5.62
  (my sql-5.5.62-win32.msi).
  - Select Typical Setup.
  - Launch the Configuration Wizard:
    - Standard Configguration
    - input a username and
      password, don't forget this!

8.) Configure IIS

- Open IIS as an administrator.
- Register PHP:
  -Go to PHP Manager -> Register
   PHP path -> C:\PHP\php-
   cgi.exe.
- Reload IIS (Stop and Start the Server)

9.) Install osTicket

 - From the osTicket-Installation-
   Files folder:
    - Unzip osTicket-v1.15.8.zip.
    - Copy the upload folder into
      C:\inetpud\wwwroot.
    - Rename the upload folder to
      osTicket (Exact Spelling!).
 - Reload IIS (Stop and Start the server).

10.) Configure osTicket 

- Open IIS:
  - Navigate to Sites -> Default ->
    osTicket.
  - On the right, click *Browse :80.
 
- Note extensions that are not enabled.
  Go back to IIS:
  - Navigate to Sites -> Default ->
    osTicket.
  - Double-click PHP Manager ->
    Click Enable or disable an
    extension.
  - Enable the following extensions:
    - php_imap.dll
    - php_intl.dll
    - php_opcache.dll

11.) Update Configuration Files

- Rename ost-config.php:
   - From:
     C:\inetpub\wwwroot\osTicket\in
     clude\ost-sampleconfig.php
  - To:
    C:\inetpub\wwwroot\osTicket\in
    clude\ost-config.php
- Assign Permissions:
  - Disable inheritance -> Remove all
    permissions.
  - Add new permissions -> Everyone
    -> Full control.

12.) Complete osTicket Setup

- In the browser, continue the osTicket
  setup:
   - Setup Helpdesk Name.
   - Set Default email (receives emails
     from customers).

13.) Install HeidiSQL and Configure
Database

- From the osTicket-Installation-
  Files folder, install HeidiSQL.
- Open HeidiSQL:
  - Create a new session: Username:
    root/ Password: root.
  - Connect to the session.
  - Create a database named
    osTicket.

14.) Finalize osTicket Installation

- In the browser, complete the setup:
    - MySQL Database: osTicket
    - MySQL Username: root
    - MySQL Password: root
- Click Install Now!

15.) Verify Installation 

 - Access your help desk login page:
   http://localhost/osTicket/scp/logi
   n.php.

Conclusion

Congratulations! You have successfully
installed and configured osTicket on your
virtual machine. Your help desk system is
now ready to use!
  
  

<p>

</p>
<p>

</p>
<br />
