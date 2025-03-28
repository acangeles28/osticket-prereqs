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

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- Enable IIS in Windows
- Install PHP manager and configure PHP
- Install Rewrite Module
- Set up my SQL Database
- Download and install osTicket

<h2>Installation Steps</h2>
<p>Create a Resource Group and Azure Virtual Machine in Windows 10</p>

![create azure RG](https://github.com/user-attachments/assets/2af1bbf4-6957-4041-8690-9cd60d33d4be)
![create a vm](https://github.com/user-attachments/assets/ec5cc559-6415-4d6f-9c19-e4ebef557a53)

<p>Log into the VM with Remote Desktop</p>

![remote desktop app](https://github.com/user-attachments/assets/cacde265-bfa1-4ed7-a057-df1e2617c8df)

<p>Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop </p>
<p>Install / Enable IIS in Windows WITH CGI </p>

![enable iis](https://github.com/user-attachments/assets/60d570aa-3fe4-4044-b72e-24f53f198e06)

<p>From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)</p>

![php directory 1](https://github.com/user-attachments/assets/92aff03e-e193-4607-84cf-28d95a7a2002)

<p>From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi) 
</p>

![rewirte module](https://github.com/user-attachments/assets/ee61ddd0-72e0-4da6-85cf-93fc2435c0df)

<p>Create the directory C:\PHP</p>
<p>From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder</p>

![php directory 2](https://github.com/user-attachments/assets/6f88da28-5a5f-45fb-ab24-91977a40a5b0)

<p>From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe</p>

![vc_redist](https://github.com/user-attachments/assets/4f90fa07-c568-4b3c-9769-7235b54fb0b9)

<p>From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi) </p>

![mysql](https://github.com/user-attachments/assets/c8701036-6ad1-45a0-b26f-8ce83ac2870c)

<p>Open IIS as an Admin</p>
<p>Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)</p>

![register php 1](https://github.com/user-attachments/assets/4bbd9784-b71d-4078-981c-995b0c088fb9)

<p>Reload IIS (Open IIS, Stop and Start the server)</p>

![reload iis](https://github.com/user-attachments/assets/25cafded-688e-470e-abbd-ed0ed0888765)

<p>Install osTicket v1.15.8
  
- From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
- Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
</p>

![install osticket 1](https://github.com/user-attachments/assets/b6b2c1ce-8136-4dac-b88e-3c9f56a932ba)
![osticket 2](https://github.com/user-attachments/assets/309af62b-d9a1-4518-866a-5a8604093a95)












<br />
