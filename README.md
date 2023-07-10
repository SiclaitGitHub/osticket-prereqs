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
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>


<img width="908" alt="Screen Shot 2023-07-10 at 1 30 29 PM" src="https://github.com/SiclaitGitHub/osticket-prereqs/assets/139138443/4f97a83e-1c37-4210-9dc1-8530cb7f91bf">


1. Set up your Azure Virtual Machine

   Create a new Azure resource group, virtual network, subnet and virtual machine running Windows 10. Choose a VM size according to your needs. Once the VM is set up, you will need to connect to it using Remote Desktop. For this, you'll need the public IP address of the VM and the credentials you provided during the VM setup.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
2. Install Web Server

 osTicket runs on a web server, so the first prerequisite to install is Internet Information Services (IIS), a flexible, secure and manageable web server for hosting anything on the web. To install IIS on your Windows 10 VM:
   
   - Open the "Server Manager" on your VM.
   - From the "Manage" menu, select "Add Roles and Features".
   - In the wizard, select "Role-based or feature-based installation" and click "Next".
   - Select your server from the server pool and click "Next".
   - In the roles list, check the box for "Web Server (IIS)" and then click "Next".
   - Click "Next" on the Features step, and then again on the Web Server Role (IIS) step.
   - Click "Install" to start the installation.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
3. Install PHP

   osTicket is written in PHP, so you need to install PHP and configure it to work with IIS.
   
   - Download PHP from the official website. Choose the VC15 x64 Non Thread Safe version that suits your needs.
   - Extract the downloaded zip file to a desired location.
   - Configure IIS to handle PHP requests by adding a module mapping. This can be done from the IIS Manager.

<br />
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


4. Install MySQL Server

   osTicket stores its data in a MySQL database, so you'll need to install MySQL Server.

   - Download MySQL Installer from the official website and run it.
   - During the setup, choose "Server only" as the setup type.
   - Proceed through the installation and configure the server as per your needs.
  
  <img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

5. Install osTicket

   - Download the latest version of osTicket from the official website.
   - Extract the contents of the archive to your web server's root directory.
   - Create a new MySQL database for osTicket using the MySQL command-line client or a tool like phpMyAdmin.
   - Navigate to your osTicket site in a web browser. You should see the osTicket installation page.
   - Follow the prompts to connect osTicket to your database and configure your new support ticket system.
