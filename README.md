<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />






<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- PHPManagerforIIS 
- rewrite_amd64
- VC_redist
- MYSQL
- Heidi

<h2>Installation Steps</h2>

<p>

  
<img src="https://i.imgur.com/2zo7XmS.png" height="80%" width="80%" alt="Disk sanitization steps"/>


</p>
<p
   
  Within the VM i  downloaded the osTicket-Installation-Files.zip and unzip it onto mi desktop.
  <ul>
    <li>without uzpping the file you would not be able to access or deploy the osTicketSoftware</li>
  </ul>

</p>
<br />

<p>

  <img src="https://i.imgur.com/N6FEy7A.png" height="80%" width="80%" alt="Disk sanitization steps"/>


</p>
<p>
In this section i  Installed/Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI
<ul>
  <li>without iis: osTicket wont run</li>
  <li>without CGI: IIS wont be able to process PHP files</li>
</ul>
</p>
<br />

<p>

<img src="https://i.imgur.com/qhx1QJz.png" height="80%" width="80%" alt="Disk sanitization steps"/>

</p>
<p>
from the “osTicket-Installation-Files” folder, i installed PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
From the “osTicket-Installation-Files” folderm i installed  the Rewrite Module (rewrite_amd64_en-US.msi) and 
Created the directory C:\PHP.
<ul>
  <li>PHP Manager for IIS is used to manage PHP installations</li>
  <li>Rewrite_x64 is neede when installing osticket because of URL Rewriting
  is essential for creating user friendly URLS</li>
</ul>

<img src="https://i.imgur.com/SPByTEO.png" height="80%" width="80%" alt="Disk sanitization steps"/>
 
</p>
<p>
From the “osTicket-Installation-Files” folder i extracted PHP folder into the “C:\PHP” folder.
<ul>
  <li> the idea is so it  can process and allow the server/operating system to properly locate and execute
  php scripts</li>
</ul>
  
</p>
<p>
  
<img src="https://i.imgur.com/YbVSIPZ.png" height="80%" width="80%" alt="Disk sanitization steps"/>
  
</p>
<p>
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
<ul>
<li>Typical Setup</li>
<li>Launch Configuration Wizard (after install) -></li>
<li>Standard Configuration -></li>
<li>Username:
    Password:
</li>
  <ul/>

</p>
<p>

  <img src="https://i.imgur.com/QDZTPHV.png" height="80%" width="80%" alt="Disk sanitization steps"/>

</p>
<p>
<ul>
<li>Open IIS as an Admin</li>
<li>Register PHP from within IIS </li>
<li>Reload IIS</li>

  
</ul>
 

  
</p>
<p>

  <img src="https://i.imgur.com/zBIYS5i.png" height="80%" width="80%" alt="Disk sanitization steps"/>

  
</p>
<p>
  uploaded folder into "c:\inetpub\wwwroot”
 vWithin “c:\inetpub\wwwroot”, Renamed “upload” to “osTicket” and Reloaded IIS

  
</p>
<p>

  <img src="https://i.imgur.com/1abwZGg.png" height="80%" width="80%" alt="Disk sanitization steps"/>

  
</p>
<p>

Some extensions are still disabled so we have to enable them.

</p>
<p>

  
 <img src="https://i.imgur.com/qRG3vtG.png" height="80%" width="80%" alt="Disk sanitization steps"/>
  
</p>
<p>

  <ul>
<li>went to  IIS, sites -> Default -> osTicket</li>
<li>Double-clicked PHP Manager</li>
<li>Clicked “Enable or disable an extension”</li>
<li>Enabled: php_imap.dll</li>
<li>Enabled: php_intl.dll</li>
<li>Enabled: php_opcache.dll</li>
<li>Refreshed the osTicket site in thr browser</li>
 </ul>
</p>
<p>

  <img src="https://i.imgur.com/65XhGBm.png" height="80%" width="80%" alt="Disk sanitization steps"/>

  
</p>
<p>
<ul>
<li>From:ost-sampleconfig.php</li>
<li>to:ost-config.php </li>
<li>Disable inheritance -> Remove All</li>
<li>New Permissions -> Everyone -> All</li>
  
</ul>
</p>
<p>

  <img src="https://i.imgur.com/dbRjlXy.png" height="80%" width="80%" alt="Disk sanitization steps"/>

  
</p>
<p>
<ul>
  <li>From the “osTicket-Installation-Files” folder, installe HeidiSQL.</li>
  <li>Created a new session, root/root.</li>
  <li>Connected to the session.</li>
  <li>Created a database called “osTicket”.</li>
  this is a database management tool
 
</ul>
  
</p>
<p>

   <img src="https://i.imgur.com/0yTQnmp.png" height="80%" width="80%" alt="Disk sanitization steps"/>

  
</p>
<p> Started setting up mi profile in the osTicket page.</p>
