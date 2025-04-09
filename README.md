![image](https://github.com/user-attachments/assets/c1b13f10-8838-458c-bf5a-5dcb27a6831d)

<h1>Azure Virtual Machines and Networking</h1>


<h2>Description</h2>
Project outlines steps to create 2 virtual machines (Windows and Ubuntu) in Microsoft Azure.  We will then remote into these VMs and monitor traffic between them using Wireshark Software.  
<br />
<h2>Environments and Utilities Used</h2>

- <b>Microsoft Azure</b>
- <b>Virtual Machines</b>
- <b>Remote Desktop Connection</b> 
- <b>Wireshark</b>
- <b>Various Network Protocols (ICMP, SSH, DHCP, DNS)</b>
- <b>Command-Line Tools</b>

<h2>Operating Systems Used </h2>

- <b>Windows 10</b>
- <b>Ubuntu 24.04</b>

<h2>Project Walk-through:</h2>
<p align="center">
Open Microsoft Azure and create a new Resource Group:

![image](https://github.com/user-attachments/assets/1d872145-3304-4923-b00c-88348790c876)

<p align="center">
Then create the Windows 10 Virtual Machine:

![image](https://github.com/user-attachments/assets/010c9b23-0804-49ab-b013-02f21d5fadea)

<p align="center">
Place the VM in the Resource Group we just created and in "Image" select the Windows 10 Pro version:

![image](https://github.com/user-attachments/assets/ccbbd7fb-b030-4e94-a992-43c654a65607)

<p align="center">
Under "Size" select "Standard_E2s_v3- 2vcpus":

![image](https://github.com/user-attachments/assets/1adbbf65-9971-4a80-9114-ad201266d589)

<p align="center">
Create the Ubuntu Virtual Machine, under "Image" select Ubuntu Server 22.04:

![image](https://github.com/user-attachments/assets/26767201-54e4-40f6-9568-10eee37a0e36)

<p align="center">
Use the same size as the previous VM:

![image](https://github.com/user-attachments/assets/b18c87f0-a18c-4387-8502-32d7b65c5e0f)

<p align="center">
Using the IP address from the Windows VM, remote into the VM, open the Web Browser and navigate to Wireshark.org
Click Download and download the version for Windows x64:

![image](https://github.com/user-attachments/assets/26563736-56b5-4dfa-8432-67c34ac130a6)

<p align="center">
Download and install Wireshark:

![image](https://github.com/user-attachments/assets/893a954f-c9db-4c7c-b856-91f1c6f730c0)

<p align="center">
Open Wireshark and begin "Packet Capture" by clicking Ethernet and then "Start Packet Capture" which is the blue shark fin:

![image](https://github.com/user-attachments/assets/175bb5a4-e73e-410a-b711-91acd7c1fc0e)

<p align="center">
Click on the search bar and enter "icmp" to filter the capture to only ping traffic:

![image](https://github.com/user-attachments/assets/d9646037-bee9-4f52-a329-e07bb4aa2799)

<p align="center">
Open Windows Powershell and "ping" the private IP address of the Linux VM.  You can now see traffic between the Windows VM (10.0.0.4) and the Linux VM (10.0.0.9):

![image](https://github.com/user-attachments/assets/f67acd79-c6c9-4ac5-897c-b6a366bad431)

<p align="center">
Initiate a "perpetual ping" from the Windows VM to the LInux VM by typing "ping 10.0.0.9 -t" into Windows Powershell:

![image](https://github.com/user-attachments/assets/82fa0343-0c39-4479-8ff2-679657148a28)

<p align="center">
We will now create a firewall within the Linux VM to block traffic incoming from the Windows VM.  In Azure, open the Linux VM and in Network Settings, click on the Network security group:

![image](https://github.com/user-attachments/assets/cf07894d-6645-4faa-8072-00cbb37073db)

<p align="center">
Under Settings, click Inbound security rules and Add an inbound security rule:

![image](https://github.com/user-attachments/assets/93870e4c-154b-438b-a9f4-267da5eda5b3)

<p align="center">
Click the boxes to deny ICMP traffic and make the Priority 290 (the highest available):

![image](https://github.com/user-attachments/assets/ac4fbfcb-f17e-41a9-aeca-52a2d88b7822)

<p align="circles">








