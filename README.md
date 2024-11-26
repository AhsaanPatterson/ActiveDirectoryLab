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



Step 15: Create an Domain
Search Server Manager
Click on “Add roles and manager”
Click on next and next once you reach this screen pause
Once you select your DC click next
After you would select “Active Directory Domain Services”
You will next, next, and then select Install
Once the installation have completed close out this screen
<br/>
<img src="https://imgur.com/C6oWpGb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>




Step 16: Click on the notification at the upper right hand corner to begin “Post deployment Configuration”
Select “ Add a new forest” and input the name mydomain.com
Input a generic password on the next screen
Click on Next when you receive the Install option and select it
Once the installation is completed the VM will automatically restart
 <br/>
<img src="https://imgur.com/jaTInQP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Step 17: Once logging back in go to the windows home icon and find underneath Windows Admin Tools  for “Active Directory Users and Computers”
Once inside of the Active Directory Users and Computers” you want to right click on mydomain.com -> New -> Organizational Unit
Create _Admins organizational group and uncheck option
Next you will right click on _Admins folder and select New -> User
You want to choose your name and standard naming convention for username
Select an generic password

  <br/>
<img src="https://imgur.com/vZduLOW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>




Step 18: Right click on your user account and select properties
Click on Members Of and select add
You want to type in domain admins and press check names
Then you want to apply and press ok
  <br/>



Step 19: Signout of the VM in order to login to newly created admin account
  <br/>
<img src="https://imgur.com/Yqr6Uau.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>




Step 20: Create RAS/NAT
Search Server Manager and select “Add roles and features”
Select next and then next, after that you want to add Remote Access
Click next again two more times you should be able to select the feature Routing
Click on next until you get the option to Install
<br/>
<img src="https://imgur.com/R2Ha3aG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Step 21: Close out of the installation and select Tools -> Routing and Remote Access
Right click on your DC and select Configure and Enable Routing and Remote Access
Select next then you want to choose the option “NAT”
You want to select the Internet option and finish the installation
If no Network Interfaces appear you may want to close out and repeat step 21 a
After the installation is complete you should see this screen
<br/>
<img src="https://imgur.com/5UngmMf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Step 22: Setup DHCP server
Go back into Server Manager and select “Add roles and features”
Click next, next and next until you receive the following screen and select DHCP
Click next until you receive the install option 
ext you want to exit out of the installer and go to tools => DHCP
Expand your DC and right click on one of the IPv4 or IPv6 -> New Scope
Click next and input the following name 




<br/>
<img src="https://imgur.com/Yqr6Uau.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Step 19: Signout of the VM in order to login to newly created admin account
  <br/>
<img src="https://imgur.com/Yqr6Uau.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Step 19: Signout of the VM in order to login to newly created admin account
  <br/>
<img src="https://imgur.com/Yqr6Uau.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Step 19: Signout of the VM in order to login to newly created admin account
  <br/>
<img src="https://imgur.com/Yqr6Uau.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Step 19: Signout of the VM in order to login to newly created admin account
  <br/>
<img src="https://imgur.com/Yqr6Uau.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


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
