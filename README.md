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
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/4.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/5.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/6.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/7.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/8.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/9.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/10.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/11.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/12.png?raw=true)
![image](https://github.com/seanmarqueling/Azure-Networking-and-RDP/blob/main/13.png?raw=true)
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

