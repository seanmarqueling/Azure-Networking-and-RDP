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

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/36.png?raw=true)

Go to the networking tab, select the virtual network (Lab2-Vnet) that was created earlier.
Click on Review + Create

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/9.png?raw=true)

Now that both Virtual Machines are created it is now time to use Remote Desktop Protocol to login to the Windows VM.

Go into Windows and search up Remote Desktop Connection
Once opened it asks for the Computer IP address. This address can be found on the Virtual Machine.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/10.png?raw=true)

Go back to the Virtual Machine page. You can find the public IP address on the right. For the Windows VM it is 20.3.248.179


![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/11.png?raw=true)

Once connected it will ask for the username and password for the Windows VM.
- Username: labexampleuser
- Passowrd: Lab123!!user

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/12.png?raw=true)

On this pop-up go ahead and click connect.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/13.png?raw=true)

Now we are connected into the windows vm. We can see on the top left corner the Public IP Address: 20.3.248.179.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/16.png?raw=true)

## - Instructions - Download Wireshark and use it to monitor traffic between the Windows VM and Linux VM

Wireshark cand be found on their webpage [Wireshark Download](https://www.wireshark.org/download.html)
I used Windows x64 Installer for this lab.


Once the application is downloaded and opened
- select Ethernet
- click on the sharkfin on the top left

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/17.png?raw=true)

The page that has opened up is where we will see all the traffic between the two VMs.

In the search bar I entered 'ICMP' so that I can monitor ICMP traffic 
- ICMP - Internet Control MEssage Protocol - this is a network layer protocol used to error reporting and diagnostic functions with IP networks. ICMP is used primarily by network devices: routers, gateways, and hosts.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/18.png?raw=true)

The first thing we want to do is check to make sure we have internet connection.

In the Windows tool bar, look up and open the application called Powershell.

In Powershell we are going to use the 'ping' command to send out an ICMP Echo Request packets to a target host.
-ping google.com
-after we pinged google two things should happen.
  - In the Powershell window we should see packets of information coming back that stgart with Reply, this means are packet went to the host and is sending a signal back.
  - In Wireshark we should now see request and reply packets from the Windows VM to Google and back.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/19.png?raw=true)

The next step is that we want to now ping traffic from the windows vm to the linux vm. What we need to do is find the private address of the linux vm.

- go to virtual machines.
- click on the name of the linux vm.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/36.5.png?raw=true)

The private IP address for the linux vm is 10.0.0.5

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/37.png?raw=true)

Now when we ping 10.0.0.5 we are able to see the traffic in wireshark from the windows vm to the linux vm.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/19.png?raw=true)

In the Wireshark application in the bottom left corner, we can click on the lines in there to expand the information about the machines.

We can see different source addresses and destination addresses.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/20.png?raw=true)

Back in Powershell, if we type in 'ipconfig /all' we can see additional information about the windows vm. In the previous image we saw code for 'Source: Microsoft_f7:ba:d3 (00:0d:3a:f7:ba:d3)

In the Powershell we can see that that infromation pertains to the physical address of the VM.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/21.png?raw=true)

Next we can do an infinite ping to the linux vm by using the following command 'ping 10.0.0.5 -t'

This will constantly send reply and request packets between the windows vm and linux vm that we can see in the wireshark traffic.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/22.png?raw=true)

We are going to block that port from receiving these ping messages.

-Go to the linux vm.
-Go into 'Networking' -> 'Network Settings'
-Click on the name of the security group 'lablinuxVM-nsg'


![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/23.png?raw=true)

-CLick on 'Settings'.
-Click on 'Inbound Security Rules'
-Click on 'Add'

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/24.png?raw=true)

Input the following to have the firewall not recieve ICMP.
-Destination port ranges: * (this is a wildcard that pertains to all ports)
Protocol: ICMPv4
Action: Deny
Priority: 290 (picking priority 290 so that it comes before all the other security rules that are in place.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/25.png?raw=true)

Once all of that is enabled we will try and ping the linux vm again.

In Powershell what we will see is a message of 'Request timed out.'

In Wireshark, all we will see are requests but we will not receive a reply.

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/26.png?raw=true)

Next we will look at ssh traffic.

-In Wireshark - type in 'ssh' to only see ssh traffic
-in Powershell the command we will use is 'ssh linuxuseradmin@10.0.0.5'
-Passwod: Lab123!!user

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/27.png?raw=true)

In powershell we should some new information pop up. To check that we are now in the linux vm we can use a couple of commands.
-id (this will give the id of the user logged in)
-hostname (this will tell you the name of the host - on this case it is linuxvm)
-uname -a (this will give you the name of the operating system)

![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/28.png?raw=true)


![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/29.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/30.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/31.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/32.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/33.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/34.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/35.png?raw=true)

