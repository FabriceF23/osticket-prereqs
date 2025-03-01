<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket: Prerequisites and Installation</h1>
<br>
This is a guide for setting up the prerequisites and installing osTicket, an open-source help desk ticketing system. 

<br>
<h2>Environments and Technologies Used</h2>

- Microsoft Azure Virtual Machine
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- IIS
- PHP Manager
- Rewrite Module
- VC_redistx86
- MySQL 5.5.62
- Heidi SQL
  
<h2>Installation Steps</h2>

<p>
</p>
<p>
<h3>Create a Virtual Machine on Azure</h3>

![image](https://github.com/user-attachments/assets/b01d699d-3471-4e3f-92ba-bc2d62cc3ba3)
<be><br>
  
- The first step is to create a Virtual Machine (VM) on Azure.
- Create a Resource Group - osTicket
- Choose Windows 10 Pro, version 22H2.
- Set the size to 2 or 4 vcpus and 16 GiB memory. I chose 4 vcpus for better performance.


![image](https://github.com/user-attachments/assets/756a4c35-ae2b-49c2-98b3-1e72874e57fc)
<br><br>

- Confirm that RDP (3389) is allowed in "Select inbound ports" to allow Remote Desktop access to the VM.</strong>
- Click on the last check box to confirm a Windows 10 license, then proceed to "Review + Create". A validation process will occur before being able to create.
</p>
<p>
</p>
<br />

<br>

<p>
<h3>Connect to your VM via the Remote Desktop Connection</h3>
<p>
  

![image](https://github.com/user-attachments/assets/a8c2a856-eeb3-4e6a-9086-05b568a2da31)
<br><br>

![image](https://github.com/user-attachments/assets/1b77fa69-3970-4465-86a2-dfc08230dfc3)
<br><br>

- Locate your VM's public IP address
- Open Remote Desktop Connection and paste the VM's IP address, then log in.</p>
<p>

</p>
<br />
<h3>Download and Unzip Installation files</h3>

![image](https://github.com/user-attachments/assets/63782d6c-68a2-4474-8e93-ca81daa7c7b0)
<br><br>

[Download zip file from here.](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)
- Unzip the files after the download is complete.

<h3>Enable IIS </h3>

![image](https://github.com/user-attachments/assets/57878805-3e92-4654-9e95-bd081b420017)
<br><br>

![image](https://github.com/user-attachments/assets/5afd9e6e-2a4d-4816-beaf-c73431a1a276)
<br><br>

<p> - Once the VM is open, we will need to install/enable IIS. Open Control Panel, Programs and click on Turn Windows features on or off</p>


<p><h2>Enable following features:</h2></p>

![image](https://github.com/user-attachments/assets/d552924d-3e54-49ac-86d1-75b71f7ac56e)
<br><br>

- Enable Internet Information Services</p>
- Expand World Wide Web Services </p>
- Expand Application Development Features
- Enable CGI
<br>
<p> Click okay and the features should be enabled.</p>
<br>
<p> <strong> NOTE: If the changes were applied successfully, type "127.0.0.1" in your browser, and this page below should appear. </strong></p>

![image](https://github.com/user-attachments/assets/d8c21692-4789-461d-bb3b-2ba2f7722b56)
<br> <br>

<h3>Install PHP Manager</h3>

![image](https://github.com/user-attachments/assets/65e3458e-2db9-48e5-914b-a3faa38bd809)
<br><br>

![image](https://github.com/user-attachments/assets/15844134-cf54-4648-93ef-ea53ee5519b8)
<br><br>

![image](https://github.com/user-attachments/assets/2efc66e8-a1e1-425c-94d2-eef8b92da586)
<br><br>

<p> Install PHP manager from the osTicket Installation Files folder.


<br>

<h3>Install the Rewrite Module</h3>

![image](https://github.com/user-attachments/assets/58b59768-0e19-4b7e-a5c3-d49ad7a34fd0)
<br><br>

![image](https://github.com/user-attachments/assets/2e3b847f-3b06-4b09-8e6b-c49e61786cee)
<br><br>

- Install the Rewrite module from the osTicket Installation Files folder


<h3>Create a new directory</h3>

![image](https://github.com/user-attachments/assets/f855ae73-c1e9-4d15-80ca-20077dd4a683)
<br><br>

<p>- Open File Explorer and create a new folder "PHP" on the C:\ directory </p>
<br>
<br>
<h3>Extract and Install PHP 7.3.8 </h3>

![image](https://github.com/user-attachments/assets/e691f85a-3056-45b7-8b55-ec4a406e1fe7)
<br><br>

- Extract the PHP zip file into C:\PHP
<br>
<h3>Install VC_redist.x86.exe </h3>

![image](https://github.com/user-attachments/assets/53af226a-985a-46d1-abbb-91de1619cd51)
<br><br>

![image](https://github.com/user-attachments/assets/2fdb9b38-4734-41b0-8cc1-ec7f93d16838)
<br><br>

<h3>Install MySQL 5.5.62 </h3>

![image](https://github.com/user-attachments/assets/8712a80f-1863-479b-a9e8-9556880ef035)

![image](https://github.com/user-attachments/assets/a93ed846-e079-4565-9616-447d23ff3db7)
<br><br>
- Select "Typical" option.

![image](https://github.com/user-attachments/assets/74f81681-d05c-44d7-8a17-4ee12dcf8f47)
<br><br>

![image](https://github.com/user-attachments/assets/a21db650-7ca0-44ea-bc00-b401738ff2d3)
<br><br>

![image](https://github.com/user-attachments/assets/ae25d1e6-db32-4794-b8b0-db822dc4585d)
<br><br>

- Launch the MySQL configuration wizard
- Choose standard configuration

![image](https://github.com/user-attachments/assets/86dfbffc-c860-4e84-8dcb-36ec5cce855e)
<br><br>
<strong>- Create username and password. Keep note of credentials. I used "root" for both to keep it simple.

![image](https://github.com/user-attachments/assets/3a9ea359-c457-4eab-844c-2ba866927119)
<br><br>

<h3>Launch IIS as an administrator</h3>

![image](https://github.com/user-attachments/assets/9ea88774-e13b-4641-874d-b08572f4ac17)
<br><br>
<p>- Search "IIS" in the Windows search bar, then right-click and select "Open as Administrator"</p>
<br>

<h3>&#9324; Register PHP Manager </h3>
<br>
- We will register PHP from within IIS. This means we are making the web server aware of the existence of the PHP on the computer.

![image](https://github.com/user-attachments/assets/9fa7b5f2-48dc-406f-b799-c8b74b39db4c)
<br><br>

![image](https://github.com/user-attachments/assets/c81b6f63-9d6a-40c0-8d93-ed34e6f994b7)
<br><br>

- Open PHP Manager
- Click on Register New PHP

![image](https://github.com/user-attachments/assets/99bbfaba-56c8-4809-be75-3229807c0e23)
<br><br>
<p> Registration will require you to provide a path to "php-cgie.exe". Lead it to the PHP folder previously created and you will find the file "php-cgi"
</strong></p>
<br>

<h3>Restart the IIS server</h3>

![image](https://github.com/user-attachments/assets/699a640b-0a78-48e6-bc9e-232e9c6fa2dd)
<br><br>
- The restart button can be found on the right side of the window under Actions and Manage Server.</p>

<br>
<h3>Install osTicket</h3>

![image](https://github.com/user-attachments/assets/af5f0ea4-cd82-41b1-8630-46751bcc995b)
<br>

![image](https://github.com/user-attachments/assets/8186aaac-c88a-4404-aa44-61d6b910c6d2)

<br>
<p>- Extract the contents of osTicket v1.15.8 from the installation files</p>
- Copy the upload for to C:\intelpub\wwwroot\
- Rename "upload" folder to "osTicket"
<br>

<h3>Restart the IIS Again.</h3>
<br>
<h3>Launch osTicket </h3>

![image](https://github.com/user-attachments/assets/4785e5d7-9258-44fe-95dc-bb8095f37d89)
<br>
- In IIS expand osTicket-VM, Sites, Default Websites, and click on osTicket
<br>

![image](https://github.com/user-attachments/assets/73a87817-4c6d-4a21-b129-571e047cee4c)
<br>

- The link is on the left side of the page under the Actions Tab. 
- Click Browse *:80 (HTTP) to launch osTicket.
<br>

![image](https://github.com/user-attachments/assets/24bcf422-d4b0-45c5-b0d2-6d1a37077491)
<br>
<p><strong>This should lead to osTicket opening in a separate Windows broswer</strong>.</p>
<br>
<h3>Enable extensions</h3>

![image](https://github.com/user-attachments/assets/c777ec3a-3616-475b-9028-8555f32df927)
<br>
- Open IIS, PHP Manager, and Select "Enable or Disable Extension". </p>
<br>

![image](https://github.com/user-attachments/assets/6a063609-d7b4-4e39-b833-278fa9d5cb97)

<p>- Enable the following extensions:</p>
<p>- Enable: php_imap.dll</p>
<p>- Enable: php_intl.dll</p>
<p>- Enable: php_opcache.dll</p>

![image](https://github.com/user-attachments/assets/b4d65f21-02ff-4f59-b6d1-8472cd1ce8ca)
<br>
- Refresh osTicket
- After refreshing your web browser on osTicket, notice more features are now available.


<h3>Rename ost-config.php</h3>

![image](https://github.com/user-attachments/assets/b4c97c22-7fad-4db8-a947-98c8547c517e)

<strong>- Note: Not doing this step may cause osTicket to work properly.
- Under c:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php, rename "ost-sampleconfig.php" to "ost-config.php"</p>
<br>
<h3>Change ost-config.php permissions</h3>

![image](https://github.com/user-attachments/assets/7d99ebb9-154c-41a1-b42e-4716c37b4634)
<br>

![image](https://github.com/user-attachments/assets/d3144c6b-d780-44bd-8ac6-1fa43bb5e111)
<br>
- Right Click ost-config.php and select properties
- Select "Security" tab and go into "Advance"
- Click Disable Heritance and select "Remove all inherited permissions"

![image](https://github.com/user-attachments/assets/937cd337-eee8-40a8-bc44-41d7193d0659)
<br>
![image](https://github.com/user-attachments/assets/cfa48bf8-5efc-46bf-972e-940874c3803a)
<br>
- Click Add, then select Principal.
- Type everyone in the object name field and click check names.
    - Note: Putting Everyone is not a good idea in a public setting. we are using it to keep the lab simple.
- Check the Full Control box.

<h3>Continue osTicket installation</h3>

![image](https://github.com/user-attachments/assets/c5b8d8c0-bca8-4384-b101-9b1c80f75044)
<br>
<p>- Continue through osTicket. Complete the form.
<p><strong>NOTE: The database credentials we'll fill out later.</strong> </p>
<br>

<h3>Install Heidi SQL from the installation files</h3>

![image](https://github.com/user-attachments/assets/e82ff8e4-b358-4d8a-993c-23cb4cddb1b8)
<br>
![image](https://github.com/user-attachments/assets/afd0151c-fab4-4465-9476-d0c350216540)
<br>
![image](https://github.com/user-attachments/assets/a1648c76-2701-41c9-906d-7354a17259ed)
<br>
- Open Heidi SQL and create a new session. Fill in the username as root and create a password. After filling up your credentials, click open and a new session should show.
<h3>Create new database </h3>

![image](https://github.com/user-attachments/assets/c1c6887d-da3a-4167-848f-ede97c53516c)
<br>
![image](https://github.com/user-attachments/assets/62f8083a-6024-44fb-9c62-cf83f849ce4d)
<br>
- On the left side of the window, right-click on "Unnamed" and click on "Database"
- Type in "osTicket" 
<br>
<h3>Finish osTicket Install</h3>

![image](https://github.com/user-attachments/assets/9e24dc6e-a219-4fd0-8c70-11d567f2e956)
<br>
- Fill out the rest of the form
- MySQL Database - osTicket
- MySQL Username - root
- MySQL Password - root

<p>Click install and osTicket should begin to set up. </p>

![image](https://github.com/user-attachments/assets/2fd540fd-a557-481a-a0b4-a1d11f29b37e)
<br>
![image](https://github.com/user-attachments/assets/7ffc6024-20bf-4c9c-a919-493bde0c0c4b)
<br>
![image](https://github.com/user-attachments/assets/f85b00ca-ed7e-48bd-baaf-96a594f373e2)
<br>
<br>
<p>The project is complete at this point.
<br>
