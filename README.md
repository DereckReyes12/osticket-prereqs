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

- Create a Virtual Machine in Azure

- Install osTicket v1.15.8

- Install HeidiSQL

- Install MySQL

- Install PHP

- install Microsoft Visual C++ Redistributable

<h2>Installation Steps</h2>


<h3 align="center">Create Virtual Machine in Azure</h3>
<br />
<h3 align="center;">First, start by creating a Resource Group inside Azure.</h3>
<br />

<p>
	<img src="https://i.imgur.com/eBi5k2l.png" height="75%" width="100%" />
</p>
<p>
<h3 align="center">Now, create a Windows 10 Virtual Machine (VM), typically with 2-4 Virtual CPUs. For username and password, it can be anything as we'll be using this info to remote in with our main computer. When creating the Virtual Machine (VM), allow Azure to create a new Virtual Network (Vnet):</h3>
<br />
</p>
<p>
	<img src="https://i.imgur.com/dEF1c7h.png" height="75%" width="100%" />
</p>
<br />
<br />
<h3 align="center;">Open your Remote Desktop Connection app on your computer and connect to your Virtual Machine that was created in Azure. </h3>
<br />
<p>
	<img src="https://github.com/Joeljjoseph1998/osticket-prereqs/assets/50834280/2e71fd86-4198-47aa-aa1a-d0aed1b8e0eb"/>
	<br />
  <h3 align="center;"> Within the VM   download the osTicket-Installation-Files.zip and unzip it onto the desktop.</h3>
  <ul>
    <li>without uzpping the file you would not be able to access or deploy the osTicketSoftware</li>
  </ul>
<p>
  <img src="https://i.imgur.com/2zo7XmS.png" height="80%" width="80%" alt="Disk sanitization steps"/>
</p>
<br />

<h3 align="center">In this section   Install/Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI.</h3>
<ul>
  <li>without iis: osTicket wont run.</li>
  <li>without CGI: IIS wont be able to process PHP files.</li>
</ul>
</p>

<p>
<img src="https://i.imgur.com/N6FEy7A.png" height="80%" width="80%" alt="Disk sanitization steps"/>
</p>
<br />
<h3 align="center">
from the “osTicket-Installation-Files” folder,install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
From the “osTicket-Installation-Files” folder,install the Rewrite Module (rewrite_amd64_en-US.msi) and 
Created the directory C:\PHP.</h3>
<ul>
  <li>PHP Manager for IIS is used to manage PHP installations</li>
  <li>Rewrite_x64 is neede when installing osticket because of URL Rewriting
  is essential for creating user friendly URLS</li>
</ul>


<p>
<img src="https://i.imgur.com/qhx1QJz.png" height="80%" width="80%" alt="Disk sanitization steps"/>
</p>
<br />

<h3 align="center">
From the “osTicket-Installation-Files” folder i extracted PHP folder into the “C:\PHP” folder.</h3>
<ul>
  <li> the idea is so it  can process and allow the server/operating system to properly locate and execute
  php scripts.</li>
</ul>
<p>
<img src="https://i.imgur.com/SPByTEO.png" height="80%" width="80%" alt="Disk sanitization steps"/>
</p>
<br />
<h3 align="center">
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.
From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)</h3>
<ul>
<li>Typical Setup</li>
<li>Launch Configuration Wizard (after install) -></li>
<li>Standard Configuration -></li>
<li>Username:</li>
<li> Password:</li>
  <ul/>
<p>
<img src="https://i.imgur.com/YbVSIPZ.png" height="80%" width="80%" alt="Disk sanitization steps"/>
</p>
<p>
<img src="https://i.imgur.com/zdhWXNx.png"height="80%" width="80%" alt="Disk sanitization steps"/>
</p>
<br />
<p>
  Download osTicket (download from within lab files: link).
</p>
<p>
	Extract and copy the “upload” folder INTO c:\inetpub\wwwroot:
</p>
	<img src="https://i.imgur.com/0MUJLMU.png" height="75%" width="100%" />
	<img src="https://i.imgur.com/1h9goM8.png" height="75%" width="100%" />
<p>
	Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”:
</p>
<p>
	<img src="https://i.imgur.com/pDikkgq.png" height="75%" width="100%" />
</p>
<br />
<br />
<h3 align="center">Reload IIS (Open IIS, Stop and Start the server)</h3>
<br />
<p>
	Go to sites -> Default -> osTicket:
</p>
<p>
	<img src="https://i.imgur.com/QeWNlG3.png" height="75%" width="100%" />
</p>
<p>
	On the right, click “Browse *:80”:
</p>
<p>
	<img src="https://i.imgur.com/3iXhNbi.png" height="75%" width="100%"/>
<br />
<h3 align="center;">Install osTicket v1.15.8</h3>
<br />

 <h3 align="center"> uploaded folder into "c:\inetpub\wwwroot”
 vWithin “c:\inetpub\wwwroot”, Renamed “upload” to “osTicket” and Reloaded IIS</h3>

<p>
  <img src="https://i.imgur.com/zBIYS5i.png" height="80%" width="80%" alt="Disk sanitization steps"/>
</p>
    <br />
<h3 align="center;">
Some extensions are still disabled so we have to enable them.</h3>
<p>
  <img src="https://i.imgur.com/1abwZGg.png" height="80%" width="80%" alt="Disk sanitization steps"/>
</p>
<br />
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
<img src="https://i.imgur.com/qRG3vtG.png" height="80%" width="80%" alt="Disk sanitization steps"/>
</p>
<br />
<h3 align="center">Refresh the osTicket site in your browser, observe the changes</h3>
<br />
<p>
	<img src="https://i.imgur.com/6iSNd4H.png" height="80%" width="100%" />
</p>
<br />
<h3 align="center">Rename</h3>
<ul>
<li>From:ost-sampleconfig.php</li>
<li>to:ost-config.php </li>
</ul>
<p>
<img src="https://i.imgur.com/65XhGBm.png" height="80%" width="100%" alt="Disk sanitization steps"/>
</p>
<br />
<h3 align="center">Assign Permissions: ost-config.php</h3>
<br />
<p>
	Disable inheritance -> Remove All:
</p>
<p>
	<img src="https://i.imgur.com/1QtRWEF.png" height="80%" width="100%" />
</p>
<p>
	New Permissions -> Everyone -> All:
</p>
<p>
	<img src="https://i.imgur.com/YzsMXNX.png" height="80%" width="100%" />
</p>
<p>
	<img src="https://i.imgur.com/k7x9yGR.png" height="80%" width="100%" />
</p>
<br />
<br />
<p>
<br />
<br />
<h3 align="center">Continue Setting up osTicket in the browser (click Continue)</h3>
<br />
<p>
	Name Helpdesk.
</p>
<p>
	Default email (receives email from customers):
</p>
<p>
	<img src="https://i.imgur.com/rvMvlNC.png" height="75%" width="100%" />
	<img src="https://i.imgur.com/YszhIpl.png" height="75%" width="100%" />
</p>
<br />
<br />
<h3 align="center">Download and Install HeidiSQL</h3>
<br />
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
	<img src="https://i.imgur.com/AEg0b2P.png" height="75%" width="100%" />
</p>
<p>
	Create a new session, root/Password1.
</p>
<p>
	Connect to the session:
</p>
<p>
	<img src="https://i.imgur.com/9t51ApR.png" height="75%" width="100%" "/>
</p>
<p>
	Create a database called “osTicket”:
</p>
<p>
	<img src="https://i.imgur.com/vXzmQqg.png" height="75%" width="100%" />
</p>
<br />
<br />
<h3 align="center">Continue Setting up osTicket in the browser</h3>
<br />
<p>MySQL Database: osTicket</p>
<p>
	MySQL Username: root
</p>
<p>
	MySQL Password: Password1:
</p>
<p>
	<img src="https://i.imgur.com/akDyber.png" height="75%" width="100%" />
</p>
<p>Click “Install Now!”</p>
<p>Congratulations, hopefully it is installed with no errors!</hp>
<p>
	<img src="https://i.imgur.com/J5omRoE.png" height="75%" width="100%" />
</p>
<br />
<br />
<h3 align="center">Clean up</h3>
<br />
<p>
	Delete: C:\inetpub\wwwroot\osTicket\setup:
</p>
<p>
	<img src="https://i.imgur.com/eg0ZPG3.png" height="75%" width="100%" />
</p>
<p>
	Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php:
</p>
<p>
	<img src="https://i.imgur.com/n6k46XL.png" height="75%" width="100%" />
</p>
<br />
<br />
<h3 align="center">Login to the osTicket Admin Panel (http://localhost/osTicket/scp/login.php)</h3>
<br />
<p>
	<img src="https://i.imgur.com/8wvWH0H.jpg" height="75%" width="100%" />
</p>
<br />
<br />
<h3 align="center"> Congrats, You've Finished Installing osTicket.</h3>
