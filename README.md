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
<img src=https://i.imgur.com/yas6tui.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
 Create a new resource group (if needed),
name the virtual machine, select the region
and the image/operating system.
<img src=https://i.imgur.com/uFUSpeO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
Select the preferred cpu size, enter 
adminstrative credentials, check the 
licensing box and review & create the VM.
No changes are needed for management,
disks, or networking sections.
<img src=https://i.imgur.com/ZTLW4q6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
2.) Accessing the Virtual Machine
</p>
Retrieve the VM's Public's IP Address and
log using **Remont Desktop** with the
credentials created during the VM setup.
<img src=https://i.imgur.com/uYp21B9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
3.) Download and Prepare
Installation Files
</p>
- Within the VM, downlaod the
  osTicket-Installation-Files.zip
  and unzip it to your desktop. The folder
  should be named osTicket-
  Installation-Files.
<img src=https://i.imgur.com/oA01ZJ7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
4.) Install IIS and Enable Required
Features
</p>
Open Control Panel -> Programs -> Turn
Windows features on or off. Install/enable
IIS with the following features:
</p>
- World Wide Web Service ->
  Application Development Features ->
  [X] CGI
<img src=https://i.imgur.com/LGR1R2d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/HlHAQo5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

5.) Install Required Components
</p>
From the osTicket-Installation-Files
folder:
</p>
- Install PHP Manager for IIS:
   PHPManagerForIIS_V1.5.0.msi.
- Install Rewrite Module:
   rewrite_amd64_en-US.msi
<img src=https://i.imgur.com/K8ibp20.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
6.) Setup PHP
</p>
- Navigate to the C: drive and create the
  directory C:\PHP
- Unzip PHP 7.3.8 (php-7.3.8-nts-
  Win32-VC15-x86.zip) into the C:\PHP
  folder.
- Install VC_redist.x86.exe.
<img src=https://i.imgur.com/5pW8bRo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/5dbQucb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/5dbQucb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
7.) Install MySQL
</p>
- From the osTicket-Installation-
  Files folder, install MySQL 5.5.62
  (my sql-5.5.62-win32.msi).
  - Select Typical Setup.
  - Launch the Configuration Wizard:
    - Standard Configguration
    - input a username and
      password, don't forget this!
<img src=https://i.imgur.com/WW2I3V2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/EVsfg4C.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/UhV2QN7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/kt6zGCq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>

</p>
8.) Configure IIS
</p>
- Open IIS as an administrator.
- Register PHP:
  -Go to PHP Manager -> Register
   PHP path -> C:\PHP\php-
   cgi.exe.
- Reload IIS (Stop and Start the Server)
<img src=https://i.imgur.com/l9EaMDd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/Hzs7jjZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/hA4aZGJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
9.) Install osTicket
</p>
 - From the osTicket-Installation-
   Files folder:
    - Unzip osTicket-v1.15.8.zip.
    - Copy the upload folder into
      C:\inetpud\wwwroot.
    - Rename the upload folder to
      osTicket (Exact Spelling!).
 - Reload IIS (Stop and Start the server).
<img src=https://i.imgur.com/sXCYOGr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/LTKA5vi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
10.) Configure osTicket 
</p>
- Open IIS:
  - Navigate to Sites -> Default ->
    osTicket.
  - On the right, click *Browse :80.
 <img src=https://i.imgur.com/LTKA5vi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <img src=https://i.imgur.com/LTKA5vi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

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
