<h1>Active Directory Home Lab</h1>


<h2>Description</h2>
In this project you will be presented a walk through how to create an Active Directory home lab Envirnoment using Oracle Virtual Box. Configuring and running this lab have helped developed my understanding of how active directory and windows networking works. 
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle Virtual Box</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Windows Server 2019</b> (21H2)

<p align="center">
Step 1: Download Virtual Box
On the left hand side select your preferred OS and download VirtualBox Platform Packages  https://www.virtualbox.org/wiki/Downloads
After installing Virtual Box you need to download the Extension Pack on the right hand side
 <br/>
<img src="https://imgur.com/RsVaMeP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 2: Download Windows 10 64 bit
https://www.microsoft.com/en-us/software-download/windows10ISO
  <br/>
<img src="https://imgur.com/y3orJ8b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 3: Download Windows Server 2019 64 Bit ISO <br/>
<img src="https://imgur.com/2XM6puk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 4: Create your 1st Virtual Machine 
Click on the “New” button in the top right hand corner
Fill out the name of you Virtual Machine and select “Other Version 64 bit” for Version
<br/>Input at least 2048MB(8GB) for the Base Memory
Select the option “Create a Virtual Hard Disk Now”
Leave the default file location and size
Click Finish once you are pleased the size
 
 <img src="https://imgur.com/Vfs9AOs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 5: In the main screen of Virtual Machine click on the “Setting”
Click on Advance settings and Select “Bidirectional” for Shared Clipboard and Drag n Drop
Scroll down to the System and select 4 CPU Processor if your computer allows
Go down to the Network section to add a 2nd NAT
You must select the Advance option to pull up multiple NATs
Make sure it is Attached to: Internal Network
<br/>
<img src="https://imgur.com/9J4s1dH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 6. Double tap on your Virtual Machine to start it
You will receive this message at first prompting you to paste the path where Windows 2019 ISO is downloaded at
Once you have added the ISO you can select the “Mount and Retry Boot” option
Depending on your PC it may take some time for the installation to begin
<br/>
<img src="https://imgur.com/PdchRYM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 7. Configure Windows Server 2019
Click on your preferred language and then begin installation
Choose the option any of the Desktop Experience
Review over License Agreement and select next
Select the custom installation option 
Click next on the following screen to begin installation
Wait till the installation completes
<br/>
<img src="https://imgur.com/nsT1E5z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Step 8: Configure your default admin password’
<br/>
<img src="https://imgur.com/SSg5IAj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>



Step 9: Press Control Alt Delete for the newly installed Windows
 <br/>
<img src="https://imgur.com/DpbVKH5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Step 10: Import CD Guest Additions
Next you want to open File Explorer inside of Virtual Machine
After you want to click on the selected program to run amd64
For the next few options up to the finalization of installation select next for default options
 <br/>
<img src="https://imgur.com/2t4sKvH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>[

Step 11: Click on the Reboot later option then manually shut down VM
 <br/>
<img src="https://imgur.com/5J8BK2f.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>



SStep 12: Log back into Virtual Machine and Prepare to configure IP address
First, click on the network icon in the lower right hand corner
Select the change adapter options 
Next select the first option right click on status then on details
You want to point out the IP address 
If the IP address start with 10 then that is the correct 1st NAT option
Now change the name of the 1st NAT to something like “Internet”
Rename the 2nd NAT to something like “Internal”

 <br/>
<img src="https://imgur.com/GEezSPK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Step 13. We will rename the PC and restart the PC after this
 <br/>
<img src="https://imgur.com/Xzam2Km.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>




Step 14. Configure IP address for NAT #2
Go to Network icon in bottom left hand corner
Click on change adapter options
Click on the Internal and press properties 
Input the following address and select ok and ok after.
IP address 172.16.0.1
Subnet Masking 255.255.255.0
Preferred DNS Server 127.0.0.1
 <br/>
<img src="https://imgur.com/fHNfoDI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>



Step 11: Click on the Reboot later option then manually shut down VM
 <br/>
<img src="https://imgur.com/5J8BK2f.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>




Step 11: Click on the Reboot later option then manually shut down VM
 <br/>
<img src="https://imgur.com/5J8BK2f.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>











</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
