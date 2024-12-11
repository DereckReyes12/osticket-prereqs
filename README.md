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

  ![Annotation 2024-12-10 191105](https://github.com/user-attachments/assets/31b6f7e3-09ea-46ad-8d00-f64e05a9016c)

</p>
<p
   
  Within the VM i  downloaded the osTicket-Installation-Files.zip and unzip it onto mi desktop.
  <ul>
    <li>without uzpping the file you would not be able to access or deploy the osTicketSoftware</li>
  </ul>

</p>
<br />

<p>

  ![cgi ](https://github.com/user-attachments/assets/aefe6c5b-c51e-43f6-8d39-852b6bb7e63b)

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

  ![Annotation 2024-12-10 200521](https://github.com/user-attachments/assets/70d19313-000d-4733-b8c3-1baf71dc175d)

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

<p>

 ![php](https://github.com/user-attachments/assets/4dce6f62-e16c-409a-a50b-af76f713c6ed)
 
</p>
<p>
From the “osTicket-Installation-Files” folder i thr  unzip PHP into the “C:\PHP” folder.
<ul>
  <li> the idea is it can process and allow the server/operating system to properly locate and execute
  php scripts</li>
</ul>
  
</p>
<p>
  
  ![Annotation 2024-12-11 142326](https://github.com/user-attachments/assets/5b19380d-b5d1-484c-9d4e-7aa0cc8a6f28)
  
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

  ![Annotation 2024-12-11 145637](https://github.com/user-attachments/assets/f55e8fa6-b6b3-494b-8a00-3cffd62e697e)

</p>
<p>
<ul>
<li>Open IIS as an Admin</li>
<li>Register PHP from within IIS </li>
<li>Reload IIS</li>

  
</ul>
 

  
</p>
<p>

  ![Annotation 2024-12-11 153543](https://github.com/user-attachments/assets/dea64d3f-a6d0-4cea-a6aa-882b81ed33eb)

  
</p>
<p>
  uploaded folder into "c:\inetpub\wwwroot”
 vWithin “c:\inetpub\wwwroot”, Renamed “upload” to “osTicket” and Reloaded IIS

  
</p>
<p>

  ![Annotation 2024-12-11 154058](https://github.com/user-attachments/assets/3c751404-cf18-4e87-bc98-d31a1736ec20)

  
</p>
<p>

Some extensions are still disabled so we have to enable them.

</p>
<p>

  ![Annotation 2024-12-11 154856](https://github.com/user-attachments/assets/5083d674-be76-4341-aa58-4780ac21ac51)

  
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

  ![Annotation 2024-12-11 155333](https://github.com/user-attachments/assets/d515cb9f-3377-4bc6-953b-a8efd51fb54f)

  
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

  ![Annotation 2024-12-11 161215](https://github.com/user-attachments/assets/5384fa90-a50a-4ffa-9b9c-2a2f01c0149d)

  
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

  ![Annotation 2024-12-11 160421](https://github.com/user-attachments/assets/2994249f-c638-43d9-9c21-e153963c6283)

  
</p>
<p> Started setting up mi profile in the osTicket page.</p>

