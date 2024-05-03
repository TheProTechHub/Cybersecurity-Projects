# WHAT IS A WINDOWS SERVER
A Windows Server is a powerful computer operating system developed by Microsoft that is specifically designed to act as a server in a networked environment. 
It provides various services and functionalities to manage and control resources, applications, and data within an organization’s network.

## Here are some key points to help understand what a Windows Server is:
Server Roles
Network Management
Centralized Storage and File Sharing
Active Directory
Application Hosting
Remote Administration Scalability and Reliability

In summary, a Windows Server is an operating system that serves as the backbone of a networked environment. It provides various server roles, network management 
capabilities, centralized storage, active directory services, application hosting, remote administration, and scalability, making it an essential tool for organizations 
to manage their network resources, ensure data security, and deliver reliable services to their users.

# WINDOWS SERVER INSTALLATION
A step-by-step guide
1. Launch VMWare, click on File > New Virtual Machine > Typical and Next.
2. Select Click on Yes and provide a name for your virtual machine and click on Next.
3. Launch VMWare, click on File > New Virtual Machine > Typical and Next.
4. Select browse and attach the server iso image and click on Next. Under easy installation, fill out the details and click on Next.
5. Click on Yes and provide a name for your virtual machine and click on Next.
6. Under disk capacity, choose 100GB, click on next to customize hardware.
7. Make sure you select the hardware resources needed for this VM. Click on close and power on the virtual machine.
8. Follow the setup wizard to complete the installation.

   <img width="869" alt="Screenshot 2024-01-17 222949" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/4c9ca8c0-7c34-4b93-865d-d4d0745fc737">

After successful installation, the windows logon screen appears. Log in and click on the start menu to launch Server Manager from there. This will be our
console for managing our server.

<img width="875" alt="pfsense-AD" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/5281f2db-a7ad-41aa-96c8-2c9a9b715012">

To verify that our DHCP configuration on our ADDS interface works, lauch the cmd and type ipconfig. The settings should indicate that our DHCP is working fine.

## Configuration of Local Sever
1. On server manager, select local server and we have a display of our system properties. Here, we will have to make some changes to help us install AD DS as a role.
2. First is to change the time zone settings. Click on change time zone > UTC > OK.

3. <img width="861" alt="Screenshot 2024-01-17 225002" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/a74c9549-9e54-4f86-b8a7-070fb45a05bc">

Secondly, we change ethernet or adpater settings. From the server manager console click on the IP address > Ethernt0 > Properties > TCP/IPv4 > Use the following IP Address. Fill in with your desired IP. Next, you choose your preferef IP for DNS services. Here we choose the default gateway IP as seen above.

4. Third configuration is to change the computer name of our server from a generic name. Click on computer name > Change > eneter the name > Click OK to restart the
   server and apply changes.
5. After all changes applied, your server manager console should be similar to this. Now, at the right top corner, click on manage > Add roles and features.
   We will install AD AS as a role in our environment.
6. Click on Next three times to server roles. Check the Active Directory Domain Services box > Add Features. Click on next three times to Confirmation.
7. Under this, click on install to begin the installation of the AD DS role.
8. After installation, click on the notification center and promote this server.
9. Check the third box and specify a name for your domain controller and click Next.
10. Enter your DSRM passowrd and select Next. With all prerequisite checks complete, click on Install.

After installation, you will need to restart the server to apply all changes.

<img width="949" alt="Screenshot 2024-01-17 225907" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/bda0a844-ca81-46c5-89d0-a450c0891ff1">

After restart, click on tools > Active Directory Users and Computers. Expand on the domain and select the Users folder, right click and choose New > User to set up a username

<img width="853" alt="Dlab" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/9a453e4c-cfc6-409b-a554-1b266fa17ce0">

Create a username and password, check password never expires box and click on Next. We have successfully created a user account on our server. 
Now we have to set up our Window client machine and join it to our Domain Controller.
<img width="868" alt="DLAB2" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/fc4fb70f-1aba-477d-8fc6-ea6ddba570d4">



# WINDOWS CLIENT INSTALLATION
A step-by-step guide
1. Choose the iso image for windows 10 and name the virtual machine.
2. SeleAfter installation, go to cmd and verify the IP settings to be sure if the server and client are on the same subnet. In this case, yes, as seen above. Go Network and
3. internet settings.ct 60GB for disk size and choose the right hardware resources for the virtual machine as seen above. Power on the VM to install.
4. After installation, go to cmd and verify the IP settings to be sure if the server and client are on the same subnet. In this case, yes, as seen above.
5. Go Network and internet settings.

6. Under network status, click on change adapter options > Ethernet0 > Properties > TCP/IPv4 > Use the following IP as the DNS. Here on the client we enter
   the IP address of the server and click on OK to apply the settings.
7. Next, open file explore, right-click on This PC and select propertites. Under computer name, click on change settings
8.
9.<img width="375" alt="client-1 test-server" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/11528cca-d213-40ab-8fd5-9f8bc5c53261">

<img width="788" alt="client-2" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/319ff682-ee81-4521-8f45-f285067dad77">


10.
11.    Under system properties, choose change > computer name and check the box Domain and enter the domain name of the server. Click OK.
   Next is to enter the Administrator credentials to restart the machine.

For a PoC, we can identify the client PC detected in our server which basically means we have successfully joinned our client machine to the server.

<img width="960" alt="client-1-EDave" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/516f21a9-0093-432e-8410-ff5241b069e1">

<img width="906" alt="client-2- sign in" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/763cda92-abcd-422d-a4f7-a58878154028">

Finally, log in to the client machine by entering the user  credentials.







   









