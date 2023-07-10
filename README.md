# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
osTicket is a widely-used and trusted open source support ticket system. It seamlessly routes inquiries created via email, web-forms, and API to a simple, easy-to-use, multi-user, web interface. osTicket comes packed with more features and tools than most of the expensive (and complex) support ticket systems on the market.
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
- PHP Manager
- Redistributable Package
- Item 4
- Item 5

<h2>Installation Steps</h2>


<img width="908" alt="Screen Shot 2023-07-10 at 1 30 29 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/4f97a83e-1c37-4210-9dc1-8530cb7f91bf">


1. Set up your Azure Virtual Machine


A virtual machine (VM) on Microsoft Azure is a computing resource that uses software instead of a physical computer to run programs and deploy apps. Each VM instance can run its own operating system (OS), which means multiple VMs can run different operating systems on the same physical machine.

Create a new Azure resource group, virtual network, subnet and virtual machine running Windows 10. Choose a VM size according to your needs. Once the VM is set up, you will need to connect to it using Remote Desktop. For this, you'll need the public IP address of the VM and the credentials you provided during the VM setup.
</p>
<br />

<p>

<img width="1072" alt="Screen Shot 2023-07-10 at 1 48 09 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/976060c0-64ba-4fdb-8048-d9ffe89e4297">

</p>
<p>
2. Install Web Server

A web server is a server that hosts websites and web applications, serving them to users over the internet. It's a computer system that processes HTTP requests, which are the core communication protocol for the World Wide Web.

osTicket runs on a web server, so the first prerequisite to install is Internet Information Services (IIS) in Windows with CGI, a flexible, secure and manageable web server for hosting anything on the web. To install IIS on your Windows 10 VM:
   
   - Open the "Control Panel" on your VM.
   - From the "Control Panel" menu, select "Programs".
   - Select "Turn Windows features on or off" under "Programs and Features".
   - Check the "Internet Information Services" box.
   - Expand the "Internet Information Services" box and select "World Wide Web Services"
   - Expand the "World Wide Web Services" box then slect and expand "Application Development Features"
   - Select "CGI".
   - Collapse the "Application Development Features" box then select and expand "Common HTTP Features".
   - Make sure all boxes under "Common HTTP Features" are checked. 
   - Click "Ok" to begin installation. 
</p>
<br />

<p>

<img width="899" alt="Screen Shot 2023-07-10 at 2 17 15 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/2f3f8615-9619-4ed3-97b8-09f3591052e0">

</p>
<p>
3. Install PHP

PHP, which stands for "PHP: Hypertext Preprocessor" (originally "Personal Home Page"), is a popular open-source, server-side scripting language that's widely used for web development. It's embedded within HTML code and used to generate dynamic content on web pages.

osTicket is written in PHP, so you need to install PHP and configure it to work with IIS.
   
   - Download PHP from the official website. Choose the VC15 x64 Non Thread Safe version that suits your needs.
   - In File Explorer create new foleder in Windows (C:) Drive titled "PHP"
   - Extract the downloaded zip file to new "PHP" folder.
   - Configure IIS to handle PHP requests by adding a module mapping. This can be done from the IIS Manager.

<br />


<img width="914" alt="Screen Shot 2023-07-10 at 2 52 06 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/caf6b9be-7293-4f69-94bc-b9cefecc0bc1">


4. Install Redistributable Package

Microsoft Visual C++ Redistributable Package  is a library file required by many applications that have been developed using Microsoft Visual C++.

When developers create software using Microsoft Visual C++, they often need to use "libraries" – collections of code that perform common functions. This way, they don't have to program these functions themselves. The Visual C++ Redistributable is exactly that: a package of libraries that software can use. The `VC_redist.x86.exe` is the installer for these libraries on a 32-bit system.


<img width="882" alt="Screen Shot 2023-07-10 at 2 54 55 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/d3953e7f-3009-49ee-8745-9a08c80d993b">

5. Install MySQL
 
MySQL is an open-source relational database management system (RDBMS) that uses Structured Query Language (SQL) to access, add, or manage content in a database. SQL is the most commonly used language for interacting with databases.

Select a "Typical" Installastion and a "Standard" Configuration when prompted after installation. 

Create log in credentials and select "Execute" to complete set up.


  
  <img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

6. Install osTicket

  - Open IIS (Run as Administrator) on VM
  - Select "PHP Manager"
  - Select "Register New PHP Version"
  - Browse to "PHP" Folder in VM Windows (C:) Drive (Via File Explorer)
  - Expand "PHP" folder and select "php-cgi" and clock "Ok".
  - Click "Resart" on PHP manager in IIS
  - 
   
