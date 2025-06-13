<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Download this link first </h2>

<p>
    <a href="https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD" target="_blank">
     osTicket-Installation-Files
    </a>
</p>


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Windows Azure Subscription
- Understand how to create a resource group/ virtual machine
- Understand how to use RDP (Remote Desktop)

Please refer to <a href="https://github.com/jeffersonshue/configure-ad" target="_blank">
Creating Virtual Machines in the Cloud
</a>

<h2> What we will complete in this project</h2>

- Create a virtual machine in Microsoft Azure
- Install osTicket
- Install MySQL
- Install HeidiSQL
- Install PHP
- Install Microsoft Visual C++

<h2>Installation Steps</h2>

1. The first step is to log into your Microsoft Azure account and head to Virtual Machines. Click on + Create and create a virtual machine
<p>
<img src="https://github.com/user-attachments/assets/b17953f1-c1fe-42d6-84da-e33e72b6089f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>

<p>

- **Create a new resource group:** `osTicket`  
- **Virtual machine name:** `osticket-vm`  
- **Select a region:** Any (just remember which one)  
- **Image:** `Windows 10 Pro, version 22Hz - x64 Gen2`  
- **Size:** Any (preferably 2/+ CPUs)  
- **Username and password:** Any (just remember them)  

</p>

2. Next, using Remote desktop, Log into your Virtual Machine using the public IP and download the osTicket ZIP file provided at the beginning of this tutorial. Open a web browser and paste the link. 
You will need to enable IIS in Windows. In the Search bar, type " Control Panel" > Under Programs click " Uninstall a program" > click "Turn Windows features on or off" > Check Internet Information Service box. You will then click into "World Wide Web Services" > Click "Application Development Features" > Check the "CGI" box. You have now enabled IIS in Windows with CGI

</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/64f2d16f-1a72-4b4e-8dcd-63c44e508112" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3 align="center"> Installing PHP Manager </h3>

<p align="center">
Inside osTicket-Installation-Files click and open "PHPManagerForIIS_V1 5.0 msi". Agree and click next, accepting all steps in order to install
</p>

![OS3](https://github.com/user-attachments/assets/897b713d-161a-4cc4-936e-b3a8d72f88e0)

<p align="center">
Inside osTicket-Installation-Files click and open "rewrite_amd64_en-US.msi". Agree and click next, accepting all steps in order to install
</p>

![OS4](https://github.com/user-attachments/assets/612230d5-d638-4332-84e2-6c24fc3399e8)

<h3 align="center"> Create directory called C:\PHP </h3>

<p align="center">
Open search bar and click on file explorer. Go to the Windows(C:) and create a new folder called "PHP". Inside osTicket-Installation-Files right click on "php-7.3.8-nts-Win32-VC15-x86.zip" and extract all, make sure to browse to the PHP folder we just created in the Windows(C:) drive. Select that folder and click extract.
</p>

![OS3 5](https://github.com/user-attachments/assets/782b2b64-6b21-42a7-b737-677e005c1397)

<h3 align="center"> Download VC_redist </h3>

<p align="center">
Click on "VC_redist.x86.exe" and click next and agree to all terms.
</p>
<br/>

![OS5](https://github.com/user-attachments/assets/5792ae54-7230-4623-a125-adb9bf76f382)

<h3 align="center"> Download MySQL </h3>

<p align="center">
Click on "MySQL 5.5.62" link right here: https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view and click next and agree to all terms. When on the Choose Setup Type screen, click on "Typical" then finish downloading. When prompted choose "Standard Configuration". For new root password and confirm just make a easy password. Can be something as easy as "root". A good practice is to have it saved on notepad in the virtual machine.
</p>
<br/>

![OS6](https://github.com/user-attachments/assets/367b7cc1-3683-46da-b561-50081c12edba)

<h3 align="center"> Configurations in IIS </h3>

<p align="center">
Open Internet Information Services (IIS) Manager in Windows search bar. Open PHP Manager > Register new PHP version > Browse to PHP folder made in Windows(:C) drive > open "php-cgi" application
</p>
<br/>

![OS7](https://github.com/user-attachments/assets/a2c0e5fa-1a2c-4a47-9c35-abd9cdd6eab4)

<p align="center">
In Internet Information Services (IIS) Manager, stop and start IIS by two ways: (1) under actions > stop > start (2) under connections > right click "osticket-vm" > stop > start
</p>
<br/>

![OS8](https://github.com/user-attachments/assets/17954909-4972-4a25-8bfb-7f0185ac7396)

<h3 align="center"> Install OsTicket </h3>

<p align="center">
In “osTicket-Installation-Files” right-click and extract "osTicket-v1.15.8.zip" into the same location ("osTicket-Installation-Files”). Copy the upload folder inside the "osTicket-v1.15.8.zip" folder we just extracted, and paste it into the Windows(C:) > inetpub > wwwroot folder. Rename the folder to "osTicket"
</p>

![OS9](https://github.com/user-attachments/assets/51f4fd46-ad68-444c-82f0-35fe05f7dfdf)

<h3 align="center"> Reload IIS </h3>

<p align="center">
Open IIS as Admin (right click on IIS and click "run as administrator" In Internet Information Services (IIS) Manager, stop and start IIS by two ways: (1) under actions > stop > start (2) under connections > right click "osticket-vm" > stop > start. Go to sites -> Default -> osTicket. On the right, click “Browse *:80”
</p>

<br/>
<p>
<img src="https://i.imgur.com/MVolxI1.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center"> OsTicket configurations </h3>

<p align="center">
Go back to IIS. Click on sites -> Default -> osTicket > Double-click PHP Manager
> Click “Enable or disable an extension”
Enable 3 things: (1) php_imap.dll (2) php_intl.dll (3) php_opcache.dll. Refresh the osTicket site in your browser, observe the changes
</p>
<br/>
<p>
<img src="https://i.imgur.com/xH9kfMd.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Rename "ost-config.php" files in Windows(C:) drive. C: > inetpub > wwwroot > osTicket > include > rename "ost-sampleconfig.php" to "ost-config.php" 
</p>

![OS11](https://github.com/user-attachments/assets/e9d6d904-fdc9-4961-8749-7745c76fb7bd)

<p align="center">
Right click "ost-config.php" > Properties > Security > Advanced > Disable Inheritance > Remove all inherited permissions from this object. Add > Select a Principal > Under "Enter the object name to select (examples) write: "everyone" > click "Check Names" > OK > Click "Full Control" > OK > highlight the only entry "Allow | Everyone" > OK. 
</p>

<h3 align="center"> Final OsTicket configurations </h3>

<p align="center">
On the osTicket Installer from the browser, click "continue".  
</p align="center">

<br/>
<ul>
  <li><strong>Helpdesk Name:</strong> whatever you want</li>
  <li><strong>Default email:</strong> make it up </li>
  <li><strong>Email:</strong> Make it up but different from the first and save (this is your admin user)</li>
  <li><strong>Username and password:</strong> Same one you made and remembered from the beginning of the tutorial</li>
</ul>
<p>
<br/>

![OS12](https://github.com/user-attachments/assets/b0cee76b-ea6a-4249-87da-d880d1851d7e)


<h3 align="center"> Install HeidiSQL </h3>

<p align="center">
Open “osTicket-Installation-Files” > HeidiSQL_12.3.0.6589_Setup > Agree and accept all terms to install. Click + New > user and password: root / root > Open
</p>

![OS13](https://github.com/user-attachments/assets/9f990eb8-7a87-4832-ba84-475bbd423672)

<p align="center">
Create database called "osTicket". Right click "Unamed" on left column > create new > database > name: "osTicket" > OK. 
</p>

![OS14](https://github.com/user-attachments/assets/117e2916-36b6-479b-b558-60c77bb88a7f)

<h3 align="center"> Continue Setting Up osTicket in Browser </h3>
<br/>
<p align="center">
MySQL Database: "osTicket" | MySQL Username: root -- MySQL Password: root > install now
</p>

![OS15](https://github.com/user-attachments/assets/7f2457ef-713b-43d7-ba8f-99806c0c53e1)

<p align="center">
Check if osTicket installed. Go back to HeidiSQL > right click osTicket in left column and click refresh. Should have a lot of new entries.
</p>
<br/>

<p align="center">
Browse to these two sites to make sure they load:
<br/>
    <a href="http://localhost/osTicket/" target="_blank">
     end users ticket
    </a>
<br/>
     <a href="http://localhost/osTicket/scp/login.php" target="_blank">
    help desk login page
    </a>
</p>
<br/>

![OS16](https://github.com/user-attachments/assets/707802d4-db71-448f-b200-24c6dc3a0798)

<h3 align="center">You did it! you are finished with the osTicket system setup!</h3>




