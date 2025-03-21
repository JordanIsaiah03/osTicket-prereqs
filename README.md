# osTicket-prereqs    <p align="center">
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

**Installation Overview**
 
1. Create Virtual Machines
2. Turn Windows 10 OS into a web server
3. Install all Prerequisite Programs
4. Install osTicket and confirm that it is a website running on the web server
5. Enable features and assign all permissions to osTicket
6. Complete installation by registering email and mySQL database
7. Confirm osTicket can be reached by end users on LocalHost
8. Clean up of all files that pose a security risk




Installation 
1. Create Resource Group 
2. Create Windows 10 Virtual Machine W/2 CPUs
3. Allow Azure to create Virtual Network (Vnet)
4. Prepare Windows 10 OS by turnint it into a web server

   ![osTicket 1](https://github.com/user-attachments/assets/ad2d8571-e072-4853-8eb8-2d8913fcf459)

 
   (https://github.com/user-attachments/assets/41b95b5e-337c-4ef0-9eee-d920f934f742)

   -Install & Enable IIS (Internet Information Services) on the Windows computer, including application features the IIS Management Console


Install Prerequisite Programs

5. Install PHP Manager
6. Install Rewrite
7. Install VC Redist
8. Install PHP:
   - Create the directory C:\PHP
   - Extract PHP files into C:\PHP directory
   - Register PHP from within IIS
   - Reload IIS (Open IIS, Stop and Start the server)

9. Install mySQL:
   - Typical Setup
   - Launch Configuration
   - Standard Configuration
   - Secret Password

10. Install HeidiSQL
    - Open HeidiSQL
    - Create a new session, root/secret password
    - Connect to session
    - Create a database called "osTicket"
   
11. Install osTicket and configure it as a website running on this web server
    - Install osTicket
    - Download osTicket
    - Extract and copy "upload" folder to C:\inetpub\wwwroot
    - Reload IIS (Open IIS, Stop and Start the server)
    - Confirm osTicket is running through the web server
      - Got to Sites -> Default -> osTicket-> "Browse *80"

12. Enable Features and assign permissions
    1. Enable Extensions in PHP Manager:
       - Enable: php_imap.dll
       - Enable: php_intl.dll
       - Enable: php_opcache.dll
    2. Rename ost-config.php:
       - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
       - To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
    3. Assign Permissions: ost-config.php
       - Disable inheritance -> Remove All
       - New Permissions -> Everyone -> All
      
13. Complete Installation by registering email and mySQL database
    1. Continue setting up osTicket in the browser
    2. Name Helpdesk
    3. Default email (receives email from customers
    4. MySQL Database: osTicket
    5. MySQL Username: root
    6. MySQL Password: (secret password)
    7. Click "Install Now"
   
14. Confirm osTicket can be reached by users on LocalHost
    1. Test link for agents and end-users:
       - Agents URL: http://localhost/osTicket/scp/login.php
       - End Users URL: http://localhost/osTicket/
      
15. Clean up files that pose a security risk
    1. Delete: C:\inetpub\wwwroot\osTicket\setup
    2. Set Permissions to "Read" only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
  
     
