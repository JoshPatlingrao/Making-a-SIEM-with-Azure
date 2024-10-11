# Making-a-SIEM-with-Azure
## Objective

The purpose of this project is to demonstrate my ability to create a VM using Microsoft Azure, setup a SIEM using Microsoft Sentinel and remediating the publicly open RDP port on the VM.

### Skills Learned
- Creating detection rules for IoCs and configuring its frequency check and severity rating.
- Creating and a configuring a VM in Microsoft Azure.
- Setting up a SIEM using Microsoft Sentinel to monitor the VM as an endpoint.

### Tools Used
- Microsoft Azure
- Microsoft Sentinel
  
## Steps

Create an account with Microsoft Azure and login to this page.

![Starting Page 1](https://github.com/user-attachments/assets/ad23ff5d-0bd7-4cfe-a8d6-50cdad4164be)
Figure X

- Click the 'Virtual Machine' icon to open the window to create a VM.

![Create Virtual Machine](https://github.com/user-attachments/assets/2e541198-fd15-453b-b97d-6ad9272c77d6)
Figure X

- Click the '+ Create' tab and select the 'Azure virtual machine with preset configuration' option.

![VM Setup 1](https://github.com/user-attachments/assets/21fdc02f-7d62-43ec-a1c0-fe2756ece75a)
Figure X

- Give the 'Resource Group' and 'Virtual Machine' a name. Do it in a similar format as shown in figure X for clarity and naming convention.
- Set the region to the one that's closest to minimise the distance lag.
- Set the image was whatever OS you prefer but for this example it would be better to stick to Windows 7, 10 or 11.
- Reason for all other options

![VM Setup 2](https://github.com/user-attachments/assets/0be0a80d-7d46-4c65-ad05-1bf965dcf80a)
Figure X

- Leave the size as the standard as shown on figure X.
- Set the user account name and password.
- As part of the project, set the 'Public Inbound Ports' to 'Allow'.
- Set the 'Select Inbound Port' as 'RDP (Port 3389)'.
- Tick the licensing box all the way at the bottom and select 'Next : Disks' to move on to the next section.
- Reason for all other options

![VM Setup 3](https://github.com/user-attachments/assets/41f00c4e-eb57-4936-9851-034ee7283153)
Figure X

- Set the 'OS Disk Size' to 127 GiB. There's no need to donwload any additional apps so it's best to keep the storage size at a minimum.
- Select 'Next : Networking' to move on to the next section.
- Reason for all other options

![VM Setup 4](https://github.com/user-attachments/assets/0508db24-1457-4571-a702-b0a1ea271417)
Figure X

- The 'Virtual Network', 'Subnet' and 'IP' should be left as is to its default setting.
- For Public Inbound Potr and Selected Inbound Port, select the same as figure X.
- 'Load Balancing' can be set to none as there won't be a high volume of traffic to the VM.
- Select 'Next : Management' to move on to the next section.

![VM Setup 5](https://github.com/user-attachments/assets/f30b708e-07bc-457c-a3ae-1a51dfc96f15)
Figure X

- Tick the box to enable the free plan for Microsoft Defender
- Continue to 'Review + Create' and leave all other settings after this at default.

![VM Setup Finish](https://github.com/user-attachments/assets/83718c36-4331-4627-80c2-d640ae7df92a)
Figure X

- The screen should be showing the VM being initialised as shown on figure X.

![Sentinel Setup 1](https://github.com/user-attachments/assets/422fd224-a5a0-4b4e-8b4d-f8fc5eadcbb3)
Figure X

- While the VM is being setup, search 'Sentinel' on the search bar and select the icon. This will bring you to the Sentinel start up page.
- Click the 'Create Microsoft Sentinel' to start the Sentinel setup.

![Sentinel Setup 2](https://github.com/user-attachments/assets/5c6a0bd4-67f4-4646-beb4-cd41530bbdef)
Figure X

- Click the 'Create New Workspace' to start.

![Sentinel Setup 3](https://github.com/user-attachments/assets/eb57e671-51a0-495b-9c80-25100f4801b3)
Figure X

- Select 'Resource Group' as the same as VM from figure X, but otherwise this should be automatically set.
- Give it a name that should match the previous naming convention.
- Set the region to the same as VM. This is to minimise or remove the distance lag when the Sentinel is logging the events in the VM.
## Summary
