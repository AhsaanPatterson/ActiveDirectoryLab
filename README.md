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
Click next and input the following name 172.16.0.100.200
Input the following information for the next screen
Start IP 172.16.0.100 End IP 172.16.0.200 and Subnet Mask 255.255.0.0
After you will hit next until you see the Configure DHCP options
Next you want to enter the following IP address and make sure to select add before moving forward
172.16.0.1
Next you want to proceed through until you see the installation 
You want to then right click on the DC and select Authorize
After you want to right click on IPv4 and refresh
<br/>
<img src="https://imgur.com/tqnCJcM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Step 23: Setup users via Powershell
Go back to Server Manager and select “Configure this local server”
Click on Internet Explorer Ehanced Security Configuration and turn it off
Open Internet Explorer and copy the following link https://github.com/joshmadakor1/AD_PS…
The link will automatically begin downloading the script files to create multiple users
Save as the folder on your desktop and extract it 
<br/>
<img src="https://imgur.com/1JQ5WQP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/8yxTPci.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/e5I9D1Y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Open the folder and names file
After add your name to the top of the names file
Open Windows Powershell ISE from the windows icon and run as admin
Once inside of Powershell click on the folder icon to locate the folder downloaded with the create users script
Once you see the script pulled up you want to type in the following command to allow scripts executable
Set-ExecutionPolicy Unrestricted
Select Yes to all after running script
Next you want to enter the following command to change directories in order to run above script
Cd C:\users\(AD name)\desktop\AD_PS-master
At this point you can press the green play button and watch the users be created<br/>
<img src="https://imgur.com/lBon7J5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/mjItyhP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/AbPKytc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/IgAsXRC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/BPKe4r7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/cV7lwBr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Step 24: Confirm changes in Active Directory
Next you want to go to the windows icon in the bottom left hand corner and select Windows Admin Tools -> Administrative Directory Users and Computers
Next you want to refresh the DC (mydomain.com) and you should see the _USERS folder and all of the newly added users
<br/>
<img src="https://imgur.com/VMvoKXx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Step 25: Create another new VM with Windows 10
Minimize your current VM and open VirtualBox.
Next you want to create a new Virtual Machine.
With this Virtual Machine you want to name it Client1 and the type Windows and version Windows 10 (64-bit).
Next you would want to set the hardware memory to 2096 MB if your computer allows that.
Click next on the following screens until you see the VM created.
Before starting right click on Client1 go to advanced settings and turn on these two options.
Go to the processor and if your computer allows it change it to 4 CPU.
After find your network tab and modify the NAT to internal then press ok.
<br/>
<img src="https://imgur.com/rkAxWLu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/jZuJcs9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="(https://imgur.com/eq0Z65Y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/lfa06LN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/5iPtnBC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/hrgaQ7i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>



Step 26: Next you want to double click on Client1 and locate the Windows10 ISO file downloaded earlier.
Wait a little time for the installation is completed and press next until you receive.
You want to select the option you do not have an license key.
Select the option Windows 10 Pro.
Next you want to select the custom option for installation type and press next to install.
Installation may take some time to complete after a while you will receive the following screen.
Select your keyboard layout.
Next option you would select “I dont have internet”.
You want to choose “Continue with limited setup”.
Type user as your account name.
You can unselect each option to help speed up time.
You can select not now option for Cortana.
<br/>
<img src="https://imgur.com/L6PvezF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/xIX95xB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/30J9dZt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/n6FKGbO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/EvNIb7x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/j5akPcB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/gHYiIOG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Step 27: Make sure Internet is connected
Open the command prompt by searching cmd.
Then enter the following command to pull up the ip addresses.
Ipconfig
If you do not see an Default Gateway be defined we must investigate from the Domain Controller.
Log back into your first VM.
Open DHCP
<br/>
<img src="https://imgur.com/QLEHUpJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Expand out the domain controller 
Expand out IPv4 and double click on Server options
After doing that you want to select more actions on the right hand plan
The selection you want to choose is “Routing” and add the following IP address below 172.16.0.1
<br/>
<img src="https://imgur.com/0PB7KMe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Step 24: Confirm changes in Active Directory
Next you want to go to the windows icon in the bottom left hand corner and select Windows Admin Tools -> Administrative Directory Users and Computers
Next you want to refresh the DC (mydomain.com) and you should see the _USERS folder and all of the newly added users
<br/>
<img src="https://imgur.com/VMvoKXx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  






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
