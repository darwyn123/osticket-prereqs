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

- Install & Enable IIS (Internet Information Services) in Windows with GGI
- Install & Configure PHP Manager for IIS (Internet Information Services)
- Install Re-write Module
- Install VC_Redistributable 
- Install MySQL
- Install HeidiSQL

<h2>Installation Steps</h2>


<h2>Install and Enable IIS (Internet Information Service) with CGI</h2>

  - Open Control Panal
  - Go to Uninstall a program, and click "Turn Windows features on or off"
  - Check box & Expand "Internet Information Services"
  - Expand "World Wide Web Services", and than "Application Development Features"
  - Check box "CGI", and click OK 

<p>
<img <img width="1143" height="665" alt="IIS_CGI" src="https://github.com/user-attachments/assets/0874ff79-26cb-4c5a-a03b-c99bb76a702b" />
</p>

<br />

<h2>Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)</h2>

  - Click "Next"
  - Than "I Agree", and Next again

<p>
<img <img width="496" height="407" alt="PHPManager" src="https://github.com/user-attachments/assets/b022b303-9280-41bc-aa93-72f0c107acf0" />
</p>

<br />

<h2>Install the Rewrite Module (rewrite_amd64_en-US.msi)</h2>

  - Click "I accept", and than "Install"

<p>
<img <img width="494" height="383" alt="Rewrite_Mod" src="https://github.com/user-attachments/assets/3af66295-0cf5-4d13-9ed7-5ebd73c88ed0" />
</p>

<br />

<h2>Create the directory C:\PHP</h2>

  - Open Windows (C:), and create folder called "PHP"
  - Unzip PHP 7.3.8 into the "C:\PHP" folder

<p>
<img <img width="615" height="517" alt="C_Drive_PHP" src="https://github.com/user-attachments/assets/a188cfa0-c3c3-4b22-aa2c-087d304c9ab8" />
</p>

<br />

<h2>Install VC_Redistributable</h2>

  - Click "I agree", and "Install"

<p>
<img <img width="481" height="297" alt="VC_Redist" src="https://github.com/user-attachments/assets/886e63a9-3d05-4553-88c3-faf1aeebfcef" />
</p>

<br />

<h2>Install MySQL</h2>

  - Click "Next", and than "I Accept", and "Next" again
  - Choose "Typical", and "Install"

<p>
<img <img width="494" height="387" alt="MySQL" src="https://github.com/user-attachments/assets/09479b33-10e6-4770-93e4-5182cb6c483e" />
 />
</p>

<br />

<h2>Configure MySQL</h2>

  - Launch the MySQL Instance Configuration Wizard
  - Choose "Standard Configuration", and click next
  - Click "Next" again
  - Create root login password, and click next
  - Execute

<p>
<img <img width="500" height="380" alt="ConfigMySQL" src="https://github.com/user-attachments/assets/cd31a42c-69fb-4d81-9f46-ce8a6a2bf29c" />
</p>

<br />

<h2>Configure PHP in IIS</h2>

  - Run IIS (Internet Information Services) as an Admin 
  - Open PHP Manager, and click "Register new PHP version" and browse to C:\PHP folder and choose php-cgi
  - Go to back to home, under Actions, under Manage Server and click "stop" than "start" to reload IIS

<p>
<img <img width="1066" height="614" alt="PHP_Register" src="https://github.com/user-attachments/assets/0996cd51-bfb5-4a29-95ae-9eb69b3a50c1" />
</p>

<br />

<h2>Install osTicket v1.15.8</h2>

  - Extract osTicket v1.15.8 folder and than open folder and copy "upload" file
  - Than open Windows (C:)> inetpub > wwwroot
  - And paste "upload" file into wwwroot
  - Than rename "upload" file (in wwwroot) to "osTicket"
  - Open IIS and Reload IIS (Stop and Start the server)
  - Go to sites > Default Web Site > osTicket, and on the right side under Browse Folder click "Browse 80(http)" 

<p>
<img <img width="889" height="755" alt="osTicket_Install" src="https://github.com/user-attachments/assets/54a3634f-8e65-435d-a05b-fea127af813d" />
</p>

<br />

<h2>More Configuration of PHP in IIS</h2>

  - Open IIS, go to sites > Default Web Site > osTicket
  - Double-click PHP Manager, and click "Enable or disable an extension"
  - Enable php_imap.dll
  - Enable php_intl.dll
  - Enable php_opcache.dll

<p>
<img <img width="909" height="613" alt="Enable_php" src="https://github.com/user-attachments/assets/0e068365-9e03-4989-a3b2-99b534d7d5f0" />
</p>

<br />

<h2>osTicket Setup</h2>

  - Open Windows (C:) > inetpub > wwwroot and open "osTicket" folder, than open "include"
  - Rename ost-sampleconfig.php to ost-config.php
  - Right click ost-config.php and click "Properties", and than go to "Security" and than "Advanced"
  - Than click on "Disable inheritance", choose "Remove all inherited permissions from this object"
  - Than click "Add" to add on new permission. Than click "Select a principal" (In this example "everyone" has permission)
  - Under "Enter the object name to select" type in "Everyone" and than click OK
  - Click box "Full control" and than OK
  - Click "Apply" and OK

<p>
<img <img width="766" height="521" alt="Add_Everyone" src="https://github.com/user-attachments/assets/30c63df8-c349-4b66-a913-39fbf649938c" />
</p>

<br />



