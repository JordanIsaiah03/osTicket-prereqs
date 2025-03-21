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

1. Azure Virutal Machine - Used to host the osTicket system
2. osTicket Installation Files - Necessary files for setting up the ticketing system.
3. HeidiSQL - A database management tool for MySQL to configure and manage the database.
   
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
4. Prepare Windows 10 OS by turning it into a web server

<img width="763" alt="Screenshot 2025-03-21 at 1 41 20 PM" src="https://github.com/user-attachments/assets/eb4e1e34-4d37-41c8-a6f3-7bd8d8da66de" />



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
       Enable Extensions in PHP Manager:
       - Enable: php_imap.dll
       - Enable: php_intl.dll
       - Enable: php_opcache.dll
       Rename ost-config.php:
       - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
       - To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
       Assign Permissions: ost-config.php
       - Disable inheritance -> Remove All
       - New Permissions -> Everyone -> All
      
13. Complete Installation by registering email and mySQL database
    - Continue setting up osTicket in the browser
    - Name Helpdesk
    - Default email (receives email from customers
    - MySQL Database: osTicket
    - MySQL Username: root
    - MySQL Password: (secret password)
    - Click "Install Now"
   
14. Confirm osTicket can be reached by users on LocalHost
       Test link for agents and end-users:
       - Agents URL: http://localhost/osTicket/scp/login.php
       - End Users URL: http://localhost/osTicket/
      
15. Clean up files that pose a security risk
    - Delete: C:\inetpub\wwwroot\osTicket\setup
    - Set Permissions to "Read" only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
  
     
