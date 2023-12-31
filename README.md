




# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
osTicket is a widely used and trusted open source support ticket system. It seamlessly routes inquiries created via email, web-forms, and API to a simple, easy-to-use, multi-user, web interface. osTicket comes packed with more features and tools than most of the expensive (and complex) support ticket systems on the market.
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com/watch?v=dEvGaxOgqf0)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Internet Information Services (IIS)
- PHP Manager / PHP Zip File
- Redistributable Package
- Rewrite Module
- MySQL Server Database
- HediSQL

  

<h2>Installation Steps</h2>


<img width="908" alt="Screen Shot 2023-07-10 at 1 30 29 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/4f97a83e-1c37-4210-9dc1-8530cb7f91bf">


1. Set up your Azure Virtual Machine

Azure is a cloud computing platform and service offered by Microsoft. It provides a wide range of cloud services that enable organizations to build, deploy, and manage applications and services through Microsoft-managed data centers.

A virtual machine (VM) on Microsoft Azure is a computing resource that uses software instead of a physical computer to run programs and deploy apps. Each VM instance can run its own operating system (OS), which means multiple VMs can run different operating systems on the same physical machine.

Create a new Azure resource group, virtual network, subnet and virtual machine running Windows 10. Choose a VM size according to your needs. Once the VM is set up, you will need to connect to it using Remote Desktop. For this, you'll need the public IP address of the VM and the credentials you provided during the VM setup.
</p>
<br />

<img width="602" alt="Screen Shot 2023-07-15 at 11 22 30 AM" src="https://github.com/SiclaitGitHub/azure-sentiel/assets/139138443/63021c1d-022d-4f60-972d-854648a0586e">

2. Connect VM1 to Microsoft Remote Desktop

SIEM stands for Security Information and Event Management. It refers to a category of software solutions and technologies that help organizations collect, analyze, and manage security event and log data from various sources across their network infrastructure.

The primary purpose of SIEM is to provide organizations with a centralized platform for real-time monitoring, detection, and response to security incidents and threats. SIEM solutions collect data from a wide range of sources, including security devices (such as firewalls, intrusion detection systems, and antivirus software), servers, applications, and network infrastructure. This data is then aggregated, correlated, and analyzed to identify patterns, anomalies, and potential security breaches.

 - Open Microsoft Remote Desktop on your local computer
 - Enter the Public IP Address of VM1
 - Enter login credentials created in Azure when setting up VM1
 - Virtual Desktop should appear upon log in.
   

<p>

<img width="1072" alt="Screen Shot 2023-07-10 at 1 48 09 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/976060c0-64ba-4fdb-8048-d9ffe89e4297">

</p>
<p>
3. Install Web Server (IIS)

A web server is a server that hosts websites and web applications, serving them to users over the internet. It's a computer system that processes HTTP requests, which are the core communication protocol for the World Wide Web.

osTicket runs on a web server, so the first prerequisite to install is Internet Information Services (IIS) in Windows with CGI, a flexible, secure and manageable web server for hosting anything on the web. To install IIS on your Windows 10 VM:
   
   - Open the "Control Panel" on your VM.
   - From the "Control Panel" menu, select "Programs".
   - Select "Turn Windows features on or off" under "Programs and Features".
   - Check the "Internet Information Services" box.
   - Expand the "Internet Information Services" box and select "World Wide Web Services"
   - Expand the "World Wide Web Services" box, then select and expand "Application Development Features"
   - Select "CGI".
   - Collapse the "Application Development Features" box, then select and expand "Common HTTP Features".
   - Make sure all boxes under "Common HTTP Features" are checked. 
   - Click "Ok" to begin installation. 
</p>
<br />

<p>

<img width="961" alt="Screen Shot 2023-07-10 at 6 18 57 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/b322f44e-fe7f-4d18-8aba-b839873bda1b">

</p>
<p>
4. Install Rewrite Module 

A rewrite module, often referred to as URL rewriting engine, is a software component that allows for the modification of incoming URL requests in a web server. The module operates based on predefined rules, allowing it to make complex changes to URLs, either for the purpose of URL redirection or to make URLs more human-readable and SEO-friendly.
   
   - Download the latest version of the Rewrite Module off of the website 


<img width="899" alt="Screen Shot 2023-07-10 at 2 17 15 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/2f3f8615-9619-4ed3-97b8-09f3591052e0">

</p>
<p>
5. Install PHP Manager

PHP, which stands for "PHP: Hypertext Preprocessor" (originally "Personal Home Page"), is a popular open-source, server-side scripting language that's widely used for web development. It's embedded within HTML code and used to generate dynamic content on web pages.

osTicket is written in PHP, so you need to install PHP and configure it to work with IIS.
   
   - Download PHP from the official website. Choose the VC15 x64 Non Thread Safe version that suits your needs.
   - In File Explorer create new folder in Windows (C:) Drive titled "PHP"
   - Extract the downloaded zip file to the new "PHP" folder.
   - Configure IIS to handle PHP requests by adding a module mapping. This can be done from the IIS Manager.

<br />


<img width="914" alt="Screen Shot 2023-07-10 at 2 52 06 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/caf6b9be-7293-4f69-94bc-b9cefecc0bc1">


6. Install Redistributable Package

Microsoft Visual C++ Redistributable Package  is a library file required by many applications that have been developed using Microsoft Visual C++.

When developers create software using Microsoft Visual C++, they often need to use "libraries" – collections of code that perform common functions. This way, they don't have to program these functions themselves. The Visual C++ Redistributable is exactly that: a package of libraries that software can use. The `VC_redist.x86.exe` is the installer for these libraries on a 32-bit system.


<img width="882" alt="Screen Shot 2023-07-10 at 2 54 55 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/d3953e7f-3009-49ee-8745-9a08c80d993b">

7. Install MySQL
 
MySQL is an open-source relational database management system (RDBMS) that uses Structured Query Language (SQL) to access, add, or manage content in a database. SQL is the most commonly used language for interacting with databases.

Select a "Typical" Installation and a "Standard" Configuration when prompted after installation. 

Create log in credentials and select "Execute" to complete set up.

<img width="829" alt="Screen Shot 2023-07-10 at 6 43 08 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/933c8225-afdc-4f4a-a3b2-131f67017bde">


8. Install osTicket

  - Open IIS (Run as Administrator) on VM.
  - Select "PHP Manager".
  - Select "Register New PHP Version".
  - Browse to "PHP" Folder in VM Windows (C:) Drive (Via File Explorer)
  - Expand "PHP" folder and select "php-cgi" and click "Ok".
  - Click "Restart" on PHP manager in IIS.
  - Download latest version of osTicket from the osTicket website.
  - Extract and copy “upload” folder to c:\inetpub\wwwroot.
  - Within c:\inetpub\wwwroot, Rename “upload” folder to “osTicket”
  - Reopen IIS and select "Restart".
  - Under the IIS Server named "VM1 (VM1\User305) select "Sites" then select "Default web Site" then select "osTicket".
  - On the "osTicket Home" page on IIS click "Browse *:80" on the right side of the page.
  - osTicket application should open in a new tab on web browser.


<img width="1072" alt="Screen Shot 2023-07-10 at 6 51 40 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/5754d0b7-3728-47fd-9e4d-ce53cb8c1190">


9. Enable PHP Extensions in IIS (PHP Manager) 

- Open IIS Manager
- Select Server (VM1\User305) then select "Site" Then "Default Web Site" Then "osTicket".
- Select "PHP Manager".
- Under "PHP Extensions" select "Enable or disable an extension".
- Enable the following extensions: "php_imap.dll" , "php_intl.dll", "php_opcache.dll".
- Refresh the osTicket window. Some of the red "x"s should appear as green checks (except the bottom two boxes).
- Open File Explorer and Browse to "Windows (C:) Drive" then select "inetpub" then select "wwwroot" the select "osTicket".
- Then Select "Include". Scroll down to the file name "ots-sampleconfig.php" and rename the file "ost-config.php".
- Right click the "ost-config.php" file and select "Properties"
- Select "Security" and then select "Advanced"
- Select "Disable Inheritance" then select "Remove all permission from this device"
- Select "Add" to add new permissions. Type "everyone" in the prompt bar and click "Check Names". Select "Everyone" and the "OK"
- Go back to the osTicket window and click "Continue".

<img width="852" alt="Screen Shot 2023-07-10 at 8 35 19 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/26a800f4-8ca7-4b71-a36a-cc7b6af334f0">


10. Complete osTicket Installation - Help Desk Credential

- Open osTciket Installation Window
- Create Helpdesk URl
- Create Admin User Credentials

<img width="941" alt="Screen Shot 2023-07-10 at 9 03 16 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/1848896f-0c90-4527-b8a2-99aeb4ac7f45">


11. Install HediSOL - Database

HeidiSQL is a lightweight, Windows-based application for managing databases. It supports various database systems such as MySQL, Microsoft SQL Server, and PostgreSQL.

HeidiSQL allows you to browse and edit data, create and edit tables, views, procedures, triggers, and scheduled events. It also offers a range of other tools for database administration, including managing user privileges, running SQL queries, importing and exporting data, and more.

-Download  and install the latest version of HediSQOl off of the website 


<img width="1213" alt="Screen Shot 2023-07-10 at 9 05 28 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/bb8a49af-34ee-434f-a982-6e52370ea1aa">


12. Create New Database Connection - HediSQL

- Selected "New" to create a new database connection.
- Login using the credential created earlier in the process then click "open".
- In the HediSQL window right click the "Unnamed" database title then select "Create new Database".
- Title the new database "osTicket".
- In the OsTicked window complete the installation prompts using the same login credentials and the MySQL database titled "osTicked".
- Click "Install Now".


<img width="1236" alt="Screen Shot 2023-07-10 at 9 29 46 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/869abda6-cefc-4a89-b94d-62a0fdc496cd">

  
13. Clean Up
    
- Delete: C:\inetpub\wwwroot\osTicket\"setup" folder
- Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
- Right click "ost-config.php" folder the select "Properties" then "Advanced" and then click "Everyone"
- Once "Everyone"  is selected click "Edit" and unselect "Write" and "Modify" permissions.
- Click "Ok"

  <img width="650" alt="Screen Shot 2023-07-10 at 9 33 49 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/730c3f5a-020c-4eae-8d7a-a46035e06246">


14. Verify osTicket Login

- Using the URL "http://localhost/osTicket/scp/index.php" log in using the credentials created earlier in the process. 








