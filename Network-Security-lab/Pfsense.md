# Pfsense
pfSense: Is an open-source firewall and router software distribution based on the FreeBSD operating system. It is designed to be installed on physical hardware or 
virtual machines to provide firewall and routing functionality. Is a versatile and feature-rich solution for individuals and organizations seeking a customizable and 
robust firewall and routing platform. Its open-source nature and active community make it a popular choice in the networking and security communities.

## Let fire it up
1.launch Vmware from your desktop. click on file file and then select new virtual machine to create a new VMware . select the default settings for the VM by choosing typical 

2. Select Browse and navigate to the folder that is saved with pfsense iso image you downloaded. You can rename your virtual machines and the location where the vm image will be saved on your host machine. Change VM name to PFSense 

3. Specify the disk capacity for the VM. By the default it 20GB Which is fine and click next.

3. Select customizse hardware to make hardware changes. we will add five more network adapters as seen in our topology and this will help ussegment our network for different traffic.

<img width="957" alt="Screenshot 2024-01-02 231513" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/fcbbaf85-83df-493f-9cbf-2255c864a176">

4. Now the VMware interface should look something like this. See that each Network adapter matches with corresponding VMnet.
Click power on this Virtual Machine to start your VM

5. Now, the installation process begins. Press enter to accept. Select install and press enter to install pfsense
we will not partitioning our VHDD. Select auto and press enter. Select install and press enter.
6. Select stripe and press enter to install pfsense
7. Select Reboot and Press Enter

### Once pfSense is installed successfully you'll intially notice two interface: WAN and LAN.
The WAN interface connect to your NAT Network adapter, allowing axxess to the internet. The LAN interface is one of the other network interfaces, but you might see only one at first . Toactivavte all other interface on pfsense choose option 1-
assign interface and we can only see two of them up (WAN and LAN) the rest re down. next step is to enable all these interface

1. Should VLANS be set up now [y:n]?: n
   enetr em0, em1, em2, em3, em4 . respectively for each consecutive question finally type (y) to proceed.

   <img width="960" alt="pfsense-4 face" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/9a129ddb-a457-4153-a842-26ab54c96d0c">

   The interface re valid but with out ipaddress. Next we have to set ip address for each interface (LAN, OPT1, OPT2, OPT3)
   and leaves out OPT4 as that interface will serve as the SPAN or MIRROR port.

1. Enter option 2. Follow this and assign IP addresses on the LAN Interface
2. follow the interface IP address assignment  and assign Ips to the remaining interface

    LAN = 172.16.0.1/24, OPT1= 192.168.100.1/24 OPT2=192.168.4.1/24 OPT3=SPANSPORT

LAN configuration

<img width="960" alt="pfsrnsr-lan-configuration" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/91eadd11-a45a-47d8-ad80-ab2b4c867662">

   You Should get something 
   
<img width="960" alt="pfsense-4 face" src="https://github.com/Davix4u/Cyber-Security/assets/130823585/9484d53e-4be9-4a53-9d94-be7c95f75d65">


Your interfaces should be like that, to make adjustment to the pfsense interface and firewall rules accesss the web configurator. in this lab, we ll be using our kali virtual machines









### Heading

# H1
## H2
### H3

### Bold

**bold text**

### Italic

*italicized text*

### Blockquote

> blockquote

### Ordered List

1. First item
2. Second item
3. Third item

### Unordered List

- First item
- Second item
- Third item

### Code

`code`

### Horizontal Rule

---

### Link



### Imag




## Extended Syntax

These elements extend the basic syntax by adding additional features. Not all Markdown applications support these elements.

### Table

| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |

### Fenced Code Block

```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

### Footnote

Here's a sentence with a footnote. [^1]

[^1]: This is the footnote.

### Heading ID

### My Great Heading {#custom-id}

### Definition List

term
: definition

### Strikethrough

~~The world is flat.~~

### Task List

- [ ] Write the press release
- [ ] Update the website
- [ ] Contact the media

### Emoji

That is so funny! :joy:



### Highlight

I need to highlight these ==very important words==.

### Subscript

H~2~O

### Superscript

X^2^
