# Azure-Networking-and-RDP
Networking Lab Overview:
The resources that will be created for this lab:
- Resource Groups
- Azure Virtual Networks and Subnets
- Azure Virtual Machines (Windows and Linux [Ubuntu])
  - Azure Network Security Groups (Firewall Resource)

Once all Azure resources are created - I am going to use Remote Desktop Protocol and Wireshark Application to monitor a traffic between the Windows VM and Linux VM.

## Instructions - Setting up the Azure Network

From the home screen of Microsoft Azure Network, either select 'Resource Groups' or enter it in the search bar on top.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/1.png?raw=true)

In the Resource Groups page, click Create.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/2.png?raw=true)

Subscription field is already selected when creating the resource group.
The two things that need to be filled out are the 'Resource Group Name' and 'Region'
In my example I am going to name it 'RG-Network-Activies' and use region '(US) West US 2.
The region itself doesn't really matter, but make sure to use the same region for everything in this particular lab
so that processes will run better.

At the bottom click on 'Review+Create'

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/3.png?raw=true)

Now that the Resource Group is created we need to create the Virtual Machines. At the top seach up Virtual Machines and click create.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/4.png?raw=true)

For the Resource group, select the one that was just made.
We need to name the virtual machine - in this case it will be called 'windows-vm'.
Next under 'Image' we are going to select our OS for the VM - Windows 10 Pro, version 22H2 - x64 Gen2

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/5.png?raw=true)

Scrolling down - we also need to select the 'Size' - Standard_D2s_v3 - 2 vcpus, 8 GiB memory

Next we need a username and password.
- Username: labexampleuser
- Password: Lab123!!user

Once that is entered, click on the 'Networking' tab

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/6.png?raw=true)

In the Networking tab we are going to create our virtual network at the same time as the virtual machine.
The Virtual Network will be called Lab2-Vnet
Click on 'Review + Create'

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/7.png?raw=true)

While Microsoft Azure is provisioning the new Virtual Machine, we are going to create an Ubuntu Virtual Machine.

For resource group select RG-Network-Activities
- Virtual machine name: lablinuxvm
- Image: Ubuntu Server 22.04 LTS - x64 Gen2

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/8.png?raw=true)

- Size: Standard_D2s-v3 - 2 vcpus, 8 GiB memory
- Under administrator account select 'password'
- username: linuxuseradmin
- password: Lab123!!user

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/9.png?raw=true)

Go to the networking tab, select the virtual network (Lab2-Vnet) that was created earlier.
Click on Review + Create

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/10.png?raw=true)

Now that both Virtual Machines are created it is now time to use Remote Desktop Protocol to login to the Windows VM.

Go into Windows and search up Remote Desktop Connection
Once opened it asks for the Computer IP address. This address can be found on the Virtual Machine.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/11.png?raw=true)

Go back to the Virtual Machine page. You can find the public IP address on the right. For the Windows VM it is 20.3.248.179

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/12.png?raw=true)

Once connected it will ask for the username and password for the Windows VM.
- Username: labexampleuser
- Passowrd: Lab123!!user

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/13.png?raw=true)

On this pop-up go ahead and click connect.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/14.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/15.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/16.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/17.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/18.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/19.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/20.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/21.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/22.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/23.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/24.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/25.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/26.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/27.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/28.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/29.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/30.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/31.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/32.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/33.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/34.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/35.png?raw=true)

