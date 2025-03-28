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
<p>Enable IIS in Windows WITH CGI </p>

  - You will need CGI to download the PHP Manager. PHP Manager is a back-end web programming language that allows osTicket to run on a web browser.
  - In the search bar, access the Control Panel, then select "Uninstall a Program." On the left, select "Turn Windows features on or off." In this list, enable Internet Information Services. Then expand the folder, look for "World Wide Web Services," expand it, look for "Application Development Features," expand it, and enable "CGI."

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

<p>Reload IIS (Open IIS, Stop and Start the server)</p>
<p>Go to sites -> Default -> osTicket On the right, click “Browse *:80”
</p>

![reload iis go to sites browse 80](https://github.com/user-attachments/assets/ff797c06-00f7-4ba3-8c97-071976a2a089)

<p>Note that some extensions are not enabled
  
  - Go back to IIS, sites -> Default -> osTicket
  - Double-click PHP Manager
  - Click “Enable or disable an extension”
    - Enable: php_imap.dll
    - Enable: php_intl.dll
    - Enable: php_intl.dll
  - Refresh the osTicket site in your browser, observe the changes
</p>

![extensions not enabled](https://github.com/user-attachments/assets/3ecd36b2-250c-4406-83f5-2aad353ef145)
![enable extentions](https://github.com/user-attachments/assets/96090855-ae2f-4067-a180-66aed492aeee)
![refresh all set](https://github.com/user-attachments/assets/46e34181-ff58-40d6-9315-9ef665078afb)

<p>Assign Permissions: ost-config.php</p>

![assign persmissions to ost-sampleconfig](https://github.com/user-attachments/assets/bfe4b294-0523-4f97-84a7-d648317bcb57)
![permissions 2](https://github.com/user-attachments/assets/ccc2cf9a-3110-4eaf-822e-fffb735d567e)

<p>From the “osTicket-Installation-Files” folder, install HeidiSQL.

  - Open Heidi SQL
  - Create a new session, root/root
  - Connect to the session
  - Create a database called “osTicket”

</p>

![heidi sql install](https://github.com/user-attachments/assets/df912d9d-00f7-43e0-8adf-ae061cae5074)
![create new heidi sql session](https://github.com/user-attachments/assets/f88e05cc-3295-445d-8503-3efd495ef6b6)
![create a database](https://github.com/user-attachments/assets/01374dd6-ffea-4ae6-85de-6785bc5336c4)
<img width="1470" alt="heidi sql database" src="https://github.com/user-attachments/assets/e6ff65b0-ecb1-434c-b990-21f65910b324" />

<p>Continue Setting up osTicket in the browser

  - MySQL Database: osTicket
  - MySQL Username: root
  - MySQL Password: root
  - Click “Install Now!”

</p>
<img width="1470" alt="Continue setting up osticket" src="https://github.com/user-attachments/assets/910136dc-1bdf-4934-bce2-17c1ab0b98d9" />

<p>Congratulations, hopefully it is installed with no errors!

  - Browse to the help desk login page: http://localhost/osTicket/scp/login.php
</p>

![osticket istalled complete](https://github.com/user-attachments/assets/f9f11339-c639-48fe-acf9-efeab5a9e05d)





<br />
