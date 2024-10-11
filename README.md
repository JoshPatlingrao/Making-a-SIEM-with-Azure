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

## Summary
