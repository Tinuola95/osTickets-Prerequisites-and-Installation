<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. To begin the lab cases i created a virtual machine in Microsoft Azure and connected through remote desktop, installing all the rquired techs.<br />


<h2>What is osTicket?</h2>

<p>
osTicket is a widely-used open source support ticket system, an attractive alternative to higher-cost and complex customer support systems - simple, lightweight, reliable, open source, web-based and easy to setup and use.
</p> 

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- Heidi SQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- osTicket Installation files
- Heidi SQL

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/jGkzvtM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Firstly, I opened throug the file explorer "Turn Windows Features on and off" to enable Internet Information Services and checked the CGI to activate it.
</p>
<br />

<p><h2><b>Files and SQL Installation</b></h2>
</p>
<p>
<img src="https://i.imgur.com/jb4mMJX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
From the pre-requisite installation files, I downloaded PHP Manager for IIS and Rewrite Module. I created the directory C:\PHP and unzipped the contents of PHP 7.3.8 inside. Now I can continue to successfully install VC_redist.x86.exe and MySQL 5.5.62. I downloaded and ran a typical SQL installation. For this demonstration, I'll use root as my username and a simple password. Execute MySQL Server Instance Configuration and close.
</p>
<br />

<p><h2><b>PHP IIS Registration</b></h2>
</p>
<p>
<img src="https://i.imgur.com/qx8pZfm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The next step is to open up Internet Information Services as an "Administrator". Open the PHP and register the C:\PHP folder that was set up prior. Reload and restart the server to apply the change that was made.
</p>
<br />

<p><h2><b>osTicket Installation</b></h2>
</p>
<p>
<img src="https://i.imgur.com/NHFCaUV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I will download and install the osTicket Zip file. Extract and copy the upload folder into the c:\inetpub\wwwroot and rename it to "osTicket". Now osTicket should be recognized by Windows, I'll open up IIS and scroll down to the osTicket folder and hit "browse 80" on the right.
</p>
<br />

<img src="https://i.imgur.com/2eoKatU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
To smoothen out the osTicket experience, I enabled these extensions inside of the IIS application:

- php_imap.dll - php_intl.dll - php_opcache
</p>
<img src="https://i.imgur.com/zhWwtMN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
I renamed: > C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php To: > C:\inetpub\wwwroot\osTicket\include\ost-config.php and configured the properties. I made sure to disable all inheritances and add a permission named "Everyone" for ease of installation.
</p>

<p><h2><b>Last cleanup steps and intialization of osTickets</b></h2>
</p>
<p>
<img src="https://i.imgur.com/4Anxi0w.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Congratulations, the setup for osTicket is complete. For the final clean up I deleted the osTicket's "setup" file and changed "ost-config" back to read only in permissions.
</p>
<br />
