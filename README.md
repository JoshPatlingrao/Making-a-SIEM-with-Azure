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

![Sentinel Setup 4](https://github.com/user-attachments/assets/30774a0f-119e-4529-82e8-b974cfa2f79c)
Figure X

- No need to set the tags. Skip to the 'Review + Create' and finish the setup.

![Sentinel Setup Finish](https://github.com/user-attachments/assets/b250638c-5153-4ea7-a902-ee7eacf34943)
Figure X

- The finished setup should show the new Sentinel as part of the work space.

![VM Connect](https://github.com/user-attachments/assets/39042aab-1c17-4edb-989d-0acfe9551fcd)
Figure X

- Type in the search bar 'VM' and go back to the VM interface. The VM should have the status set to 'Running'.

![VM Connect 2](https://github.com/user-attachments/assets/b9146ad8-07d5-4689-805a-05a81ad8151c)
Figure X

- Select the VM and go to 'Overview'. As shown on figure X, this will provide the specifications of the machine and it should match the ones et on the previous steps.
- Go to 'Networking' then to 'Networking Settings' to confirm that the VM allows for RDP connection.

![Sentinel Add](https://github.com/user-attachments/assets/31b19217-48ae-49db-9c85-084dbc6d14c6)
Figure X

- Go back to the Sentinel page, select the Sentinel that was set up and click 'Add' to add to the workspace.

![Sentinel Overview](https://github.com/user-attachments/assets/96c2d4ad-41cf-4f39-9c2b-eb868a5538d7)
Figure X

- Select the Sentinel again and open the 'Overview' page. This will display the Incidents, Automation, Data and Analytics regarding the events happening on the VM.

![Log Analytics Workspace](https://github.com/user-attachments/assets/bebc5ea1-62c5-4a99-abef-237b1ed3bfb0)
Figure X

- To do this, go back to the Analytics Workspace through the search bar and open the Analytics that has been setup.
  - The Analytics will process the event logs from the VM before passing it to the Sentinel.
 
![Sentinel Data Connectors](https://github.com/user-attachments/assets/d0185f40-4e33-4bd2-a9f0-54e7bff84abd)
Figure X
- Go to 'Configuration' then 'Data Connectors'.
  - This is where the Log Analytics can 'connect' to a source of log events.
- Click on 'Content Hub'.

![Content Hub Install](https://github.com/user-attachments/assets/b1c0a0cb-e5b2-451f-b2ee-bf8d8abb5a21)
Figure X

- Type 'Azure Monitor Agent' on the search bar.
  - While there are many connectors, the one we'll be using is the 'Azure Monitor Agent'.
- Select the 'Windows Security Event' and click 'Install'.
- Wait until the statuc displays 'Installed'.

![Updated Connectors](https://github.com/user-attachments/assets/c26e85ab-a2d4-4da7-a99e-1f1a2d9edc8c)
Figure X

- Go back to the 'Microsoft Sentinel' page.
- Select the log analytics, go to 'Configuration', then 'Data Connectors'.
  - This should display the installed data connectors.
  - If it doesn't, then click 'Refresh'.
 
![Open Connector Page](https://github.com/user-attachments/assets/4216928b-1833-41a4-9247-19a0fdddadba)
Figure X

- Select the 'Windows Security Events via AMA' and click 'Open Connector Page'.

![Data Connector Setup 1](https://github.com/user-attachments/assets/7b08e1da-8b81-4aa6-be7b-d8b014ddafb4)
Figure X

- This page should open and click 'Create Data Collection Rule'.
- Give the rule a name.
- Make sure its resource group is the same as the VM.

![Data Connector Setup 2](https://github.com/user-attachments/assets/194cf0d1-d5ea-4aaa-99f0-223a1c743757)
Figure X

- Select the VM and click 'Next : Collect'.

![Data Connector Setup 2](https://github.com/user-attachments/assets/fc99ba59-5b57-4112-bb62-d548f8397b69)
Figure X

- Select 'All Secrutiy Events' and click 'Next : Review + Create'.
- Finish the setup.

![Query Log](https://github.com/user-attachments/assets/d0b0b28d-52cb-48e5-84cb-ec13806f4cec)
Figure X

- Go back to the Sentinel page, select the log analytics and go to 'Logs'.
- Go to 'Microsoft Sentinel' tab and Select 'Secruity Event'.
- Click 'Run'
  - This will show the brute force attempts to use RDP to access the VM that has occured so far.
 
![Query Log 3](https://github.com/user-attachments/assets/762ebf6d-e533-4b53-b5ba-60cfc1dfc483)
Figure X

- Set the filter to 'SecurityEvent | where Activity contains "success" and Account !contain "system"'.
  - The "success" keyword in the 'Activity' field indicates that a succesful login has occured which is the priority over the failed logins.
  - The "system" keyword in the 'Account' field is filtered out to remove succesful login events which may have been done by a system account.
  - The combination of these filters should only display succesful login events that have been initated through an RDP.
## Summary
