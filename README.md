<p align="center"><img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/></p>

<h1>osTicket - Prerequisites and Installation</h1>
This guide will walk you through how to set up the open-source help desk ticketing system osTicket on your Windows 10 computer.

<h2>What You’ll Need</h2>

<ul>
    <li>Microsoft Azure (to create a virtual machine)</li>
    <li>Remote Desktop</li>
    <li>Internet Information Services (IIS)</li>
    <li>PHP, MySQL, and a few other tools</li>
</ul>

<h2>Operating System</h2>

<ul>
    <li>Windows 10 (version 21H2)</li>
</ul>

<h2>Things to Install Before You Begin</h2>

<ul>
    <li>Enable IIS with CGI</li>
    <li>Install PHP Manager and the Rewrite Module</li>
    <li>Install Microsoft Visual C++ Redistributables</li>
    <li>MySQL</li>
    <li>HeidiSQL (to manage your database)</li>
    <li>osTicket version 1.15.8</li>
</ul>
You can download everything you need here: [Download Link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

<h2>Step-by-Step Installation</h2>

<h3>1. Set Up a Virtual Machine</h3>
Go to <a href="https://portal.azure.com/">Azure Portal</a> and create a virtual machine (VM) with Windows 10 Pro. Make sure it has at least 2 CPUs and 16GB of RAM for a smooth experience.

<h3>2. Connect to Your Virtual Machine</h3>
Use Remote Desktop to connect to your VM with the public IP address assigned to it.

![image](https://github.com/user-attachments/assets/7b15e6d0-7986-4339-954b-c74461cb806b)

<h3>3. Enable IIS (Internet Information Services) with CGI</h3>
<ul>
    <li>Once you're in, open <strong>Control Panel</strong> → <strong>Programs</strong> → <strong>Turn Windows Features On or Off</strong>.</li>
    <li>Make sure you check <strong>Internet Information Services (IIS)</strong>, and also <strong>CGI</strong> and <strong>Common HTTP Features</strong>. This will install the necessary web server features for osTicket.</li>
</ul>

![image](https://github.com/user-attachments/assets/c304f75d-e39b-4c16-9a9a-52736b8fcf13)

<h3>4. Install PHP Manager</h3>
Run the PHP Manager installer from your downloaded files and follow the steps in the installer.

![image](https://github.com/user-attachments/assets/df6047ac-4c45-457e-8c07-51fe7087ff8a)

<h3>5. Install the Rewrite Module</h3>
Next, download and install the <strong>Rewrite Module</strong> using its installer.

![image](https://github.com/user-attachments/assets/41bf827b-5dc1-4666-81ec-1a4ecef20083)

<h3>6. Install Microsoft Visual C++ Redistributables</h3>
Install the <strong>Visual C++ Redistributables</strong> by running the installer.

![image](https://github.com/user-attachments/assets/62ffa7f0-fe11-4fa9-8641-620d30510cfa)

<h3>7. Set Up the PHP Folder</h3>
Create a folder called <strong>PHP</strong> on your C: drive and unzip the <strong>PHP 7.3.8</strong> files into this folder.

![image](https://github.com/user-attachments/assets/8caacf1a-6f66-4e81-9d9d-d645a77550c2)

<h3>8. Install MySQL</h3>
Download and install <strong>MySQL 5.5.62</strong>. During installation, set the root password to <strong>Password1</strong>.

![image](https://github.com/user-attachments/assets/dfe24f4b-2574-4ad7-8da7-59429e3ad9af)

<h3>9. Register PHP in IIS</h3>
<ul>
    <li>Open IIS from the Start Menu and run it as administrator.</li>
    <li>In IIS, click <strong>PHP Manager</strong>, then select to register the PHP version you installed by choosing the <strong>php-cgi.exe</strong> file from the <strong>C:\PHP</strong> folder.</li>
</ul>

![image](https://github.com/user-attachments/assets/db0ad21c-4bba-42f3-aa9e-840d38e27d3a)

<h3>10. Install osTicket</h3>
<ul>
    <li>Run the osTicket installer and move the <strong>upload</strong> folder from the installer to <strong>C:\inetpub\wwwroot</strong>.</li>
    <li>Rename the <strong>upload</strong> folder to <strong>osTicket</strong> (make sure the name is exactly as it is).</li>
    <li>Restart IIS to apply the changes.</li>
</ul>

![image](https://github.com/user-attachments/assets/4787f247-6e30-47f4-a204-e32d7cedb556)

<h3>11. Enable PHP Extensions</h3>
Go to IIS → <strong>osTicket</strong> → <strong>PHP Manager</strong> → <strong>Enable or disable an extension</strong>. Enable the following:
<ul>
    <li>php_imap.dll</li>
    <li>php_intl.dll</li>
    <li>php_opcache.dll</li>
</ul>
These extensions are needed for osTicket to work correctly, like handling emails and improving performance.

![image](https://github.com/user-attachments/assets/28788a88-6726-4f3b-897b-73ee05072d95)

<h3>12. Configure osTicket</h3>
<ul>
    <li>In the <strong>C:\inetpub\wwwroot\osTicket\include</strong> folder, rename <strong>ost-sampleconfig.php</strong> to <strong>ost-config.php</strong>.</li>
    <li>Right-click the <strong>ost-config.php</strong> file, go to <strong>Properties</strong> → <strong>Security</strong>, then click <strong>Advanced</strong>. Disable inheritance, then click <strong>Remove all inherited permissions</strong>.</li>
    <li>Add <strong>"Everyone"</strong> with full control.</li>
</ul>

![image](https://github.com/user-attachments/assets/9fef83c8-e613-4382-a890-fe3bce0d2ca3)

<h3>13. Set Up the Database</h3>
<ul>
    <li>Open <strong>HeidiSQL</strong> and log in with <strong>root</strong> as the username and <strong>Password1</strong> as the password.</li>
    <li>In HeidiSQL, create a new database called <strong>osTicket</strong>.</li>
    <li>Go back to the osTicket setup page in your browser, and under the Database section, enter <strong>osTicket</strong> as the database name.</li>
</ul>

![image](https://github.com/user-attachments/assets/8315ed50-aee5-4bf8-bdc1-cda8bef49b0f)

<h3>14. Finish the Installation</h3>
<ul>
    <li>On the osTicket setup page, enter <strong>adminuser</strong> for the admin username and <strong>Password1</strong> for the password.</li>
    <li>Fill out the rest of the form, but leave the Database Settings section as is for now.</li>
    <li>Click <strong>Continue</strong>.</li>
</ul>

<h3>15. Final Step: Test osTicket</h3>
Once everything is set up, you can log into osTicket using your admin credentials.

![image](https://github.com/user-attachments/assets/a6af7eb7-8430-45be-840c-f6bccca2c3c6)

<h2>Great! now You’ve Successfully Installed osTicket!</h2>
