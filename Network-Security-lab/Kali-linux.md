NAT Door: This door faces the internet, like a window to see whats happenning out there
Other Doors: We have 5 more doors for special tasks, like making sure only good stuff get through by monitoring

<img width="950" alt="kali-pfsense-4-face " src="https://github.com/Davix4u/Cyber-Security/assets/130823585/4c7f167e-aba5-4aab-b22b-e76918673fcc">

Select edit virtual machine as seen above, allocate resources to the attack machine (memory, cpu, network adapter) and click OK. Finally, click on Power on this 
virtual machine to boot up the VM.
Enter the username and password for kali and by default it is kali kali

<img width="849" alt="kali-kali" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/d0f3ef33-41d9-4aa1-b186-c0df4dc99c7d">

Go to terminal and type the command ifconfig and here, we could see that our firewall has assigned an IP to our attack VM. Next, we have to access the web interface of the firewall.

Launch Mozilla Firefox and type http://172.16.0.1 to access the pfSense. Default username and password is admin:pfsense and press enter.
<img width="866" alt="kali-pfsense-admin" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/31fb0af0-8eb3-42f2-b42d-f024422ba690">

CONFIGURATION STEPS FOR PFSENSE ON KALI
1. After successful login, you will be greeted with a welcome screen to setup the firewall. Follow this and click on next.
2. Here, you can choose your time zone and click on next. On the next page, scroll all the way down and uncheck the RFC options below and click on Next.
3. On the LAN interface we leave all as default and click on Next. Final step, you change the default password and select Next.
4. Select Reload and Finish to get done with the initial set up configuration.

<img width="845" alt="Pfsense dashboard" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/1639e03e-953c-4c32-a3ff-796983eed6a0">

<img width="853" alt="Screenshot 2024-01-17 205731" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/f24d1994-75e3-4ffa-a90b-67ec2df5bc7e">

Now, we need to assign names to all the interfaces as it is in our topology. So, at the top menu, select interfaces > LAN. Change the hostname to Admin, leave everything at default and click on save and apply changes.

NB: Do same for interfaces OPT1 = Ubuntu, OPT2 = AD DS, OPT3 = SIEM & OPT4 = Span Port accordingly.

For interface OPT4, make sure to check enable interface and name it Span Port as this will serve as the interface for monitoring in our network. Click on Save and apply changes.

<img width="863" alt="pfsense-interface-assignment" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/46b87224-13aa-4472-aef4-a45c6951c57c">

At the top menu, click on interfaces > Assignments. This should list all the interfaces on our firewall, with the assigned names and associated MAC Address.

<img width="585" alt="Screenshot 2024-01-17 212037" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/358c121d-3f31-439e-bc8f-f3aed3aecd34">

We need to now bridge the interface we want to monitor to our span port. In this lab, the interface we will be monitoring is our AD DS environment. Go to the interfaces page, click on Bridges. Select the Add button to bridge our AD DS interface to the Span Port and click on display advanced

<img width="846" alt="Screenshot 2024-01-02 233852" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/54126910-54ca-4a06-a7b6-81d4d9e201ee">

Under advanced configuration, scroll down to span port and add that interface as a bridge for monitoring as shown above

Next, we need to set up a firewall rule on our WAN interface to allow connectivity to the internet. At the top, select firewall > rules. Select WAN > Add.

<img width="933" alt="Screenshot 2024-01-17 214426" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/1997f7ee-96f1-4fae-937f-6b312efa1a02">

Under action choose Pass. Under protocol select Any and apply changes to save the settings.
Congratulations! You’ve successfully set up KALI as a virtual machine and configuring the firewall, taking a significant step towards building your own network environment.













