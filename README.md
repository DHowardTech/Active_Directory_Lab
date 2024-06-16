# Active_Directory_Lab
 Window Server 2019/Active Directory Home Lab

1.	Download and install Oracle VirtualBox *
2.	Download Windows 10 *

![Screenshot 2024-06-06 185713](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/6276206b-7b13-4e31-b99c-08baf78026d5)

3.	Download Windows Server 2016/2019/2022 *
   
 ![Window 2019 Server Download](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/653984f1-a78b-41d3-bd33-009ed1f39b98)

5.	Create a Windows Server (Domain Controller Virtual Machine *
   
 ![Dom  Ctrlr Summary](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/28140386-16d3-447f-a08a-0a0176f2766d)

7.	Insert Guess Additions to CD Image to Domain Controller *
   
    ![Win2022Server Guest Addition](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/aaef9e60-0033-455a-838d-3481d3bdd7f6)
  	
9.	Set Up IP Addressing: Go to network& internet settings, click change adapter settings, identify & rename each NIC adapter by right-clicking and selecting status: 10.x.X.x is external int, whereas 169.X.X.X is due to trouble with DHCP and after obtaining a real IP address. Right-click the internal network. *
    ![Win2022Server IP Config](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/1d56cf1e-84b3-4711-a915-21a9a5b3bfb9)
   	
10.	Rename the PC: Settings -> About -> Click Rename This PC *
    
11.	Install Active Directory Domain Services: Click Add roles and feature in server mgr, click next, leave role-based or feature-based installation selected and click next, ensure “select a server from the server pool” is selected, and make sure the desired server is selected in the server pool, click next, select “Active Directory Domain Services” box, click “Add Features”, click next until you can click install.  *
    
    ![Selection of Win2022Server in Pool](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/b8eed93d-1981-4a91-92ca-db559bee4883)

    ![Win2022Server AD Setup](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/441a2025-9884-45cb-b7dd-90bd8c2af7c2)
   	
13.	Post Deployment Configuration: Click on the Flag with a yellow triangle with an exclamation point to bring down the Post Deployment notification, and select the notification. Select “Add a new forest” from the “Select the deployment operation”. Enter your desired Root Domain name: ex: mydomain.com. Click next. Enter a simple password (e.g., password1!), Click next to Allow the verification of NetBIOS of the domain, then click next until you can install. After installation, the system/instance will restart. *
    
![Win2022Serve Post-Deployment Config](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/63d10aef-35ae-4961-bc08-ea555921b7e3)

10. Check AD Admin Login is complete.
    
    ![Completed AD](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/3d4d7801-d99f-48d5-b334-ce47246db930)
    
12.	Create a Dedicated Domain Admin Account/	Create an Admin Organizational Unit: Click the start menu, select Windows Admin Tools, and select Active Directory Users and Computers. Right-click the newly created domain, select New, then select Organization Unit.

 ![Creation of ADMIN OU](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/f87c9502-6034-4794-8c6c-2f330a2ca3f2)

12.	Create a New User Account under the new OU: Right-click the newly created Admin OU, select new, then select User. Enter the User’s information and click next. Enter new user’s password (this example: password1!) Select the appropriate box (user must change password at next login -password reset, User can’t change password – only admin can change password, Password never expires – typical, account is disabled -disables an account).
    
    ![Addition of User](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/5b5ea99b-fc45-4704-bffa-5982ede5ddde)
   	
13.	Assign New User to Domain Admin: Click on Admin Ou, right-click on user, select properties, select Member OF tab, Select Add.., In the text box -enter “Domain Admin”, select Check Names on the right side to resolve the object name, click OK to exit member of the box, then click apply. *
	
    ![Adding New User to Admin OU](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/656d2660-5e7e-4c31-8d21-0e7036f6b26c)

14.	Check the login of the newly created user: Log/Sign of Domain ctrl, and attempt to sign in with the user’s credentials.
    
    ![Successful New Admin Login](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/adf1d4c5-5f5b-4ec7-a0af-7bda061a3fd3)
   	
28.	Install Routing and Remote Access /NAT(to allow the client computer which is on a private network to access the internet through our domain controller):
    
   ![Add Remote Access and Routing Feature](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/29dcfed5-3211-4b7c-90ea-0b31bc9d58a8)
   
30.	Click “Add roles and features in server mgr.”, select role-based or feature-based installation and click next, select “a server from the server pool” radio button ensuring your desire server is selected from the server pool then click next, select “Remote access” box and click next, Click next again until you come upon three options: Web Application Proxy, Routing, DirectAccess and VPN - select routing, Another option will be automatically selected, which is okay. Click next until you can select install. Click install and allow it to finish the installation. select Tools in Server Mgr. Select Routing and Remote Access. Right click Domain Controller and select “Configure and Enable Routing and Remote Access”.

    ![Routing and Remote Access Config](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/085ef30e-bd5a-443c-b176-6dc999966847)
   	
   ![Add Remote Access and Routing Feature PT 2](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/6376509c-0267-427a-ad23-8c95a666e199)

32.	Click next. Select the Network Address Translation (NAT) radio button and click next.
33.	![Routing and Remote Access Config Pt  2](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/5b897fa7-13a9-4f7f-a387-7099b09e70fd)
   
34.	  Select the external network from the dialog box in the “Use this public interface to connect to the Internet” and click next. NOTE: if there aren’t any public networks being shown, exit out of the Routing and Remote access and open it up again. Click next until you can click finish.
    
   ![Routing and Remote Access Config  Pt  3](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/a23be8bd-85fa-433a-a9f9-13de8373110b)


31.	Setup DHCP Server on Domain Controller: Click “Add roles and features in server mgr”, select role-based or feature-based installation, and click next, select “a server from the server pool” radio button ensuring your desired server is selected from the server pool then click next, select DHCP server tab/box, click add features.
    
    ![DHCP Config  Pt  1](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/9ecd5bd0-412f-40c2-8a48-62e00bc4cd1d)

    ![DHCP Config  Pt  2](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/678dad32-1604-42b9-8922-a793a67dd86d)
   	
33.	Configure DHCP: Click tools in Server Mgr., Click DHCP from the selection, Click the domain ctrl, right-click the IPv4 server in the middle section, select new scope, Assign a New Scope name after the scope range: e.g., 172.16.0.100-200
    
    ![DHCP Config  Pt  3 - Creating New Scope](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/f6515611-c3d5-41b4-8522-57e10e42169f)
   	
35.	Lease Duration: Depends on the situation. For this project, set up for eight (8) days.
    
    ![DHCP Lease](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/bf5de1f4-9281-41c7-a057-ac69429be81e)
   	
37.	DHCP Options: Click “Yes, I want to configure these options now” to assign an IP address for the Default Gateway or Router.
    
39.	Add IP Address for Router: Enter default address for IP ex. 172.16.0.1, click next to use the domain controller as the parent domain. Click next. Ignore the WINS server, and click next. Select “Yes, I want to activate the scope now” To activate the domain scope, click next. Click finish.
    
    ![DHCP Config Pt  4 - Adding IP Address Range](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/350a6d15-68c7-4e6a-be3e-2eeaa9fca1cb)
   	
41.	Authorize DHCP server: right-click domain controller in the DHCP window, select authorize, and click refresh.
    
43.	OPTIONAL: To allow internet connection: click on Local Server in the Server Mgr, scroll until you see “IE enhanced Security Config”, click the “On” hyperlink, and turn off Admin and User Config.
    
45.	Add User using PowerShell Script: Open Windows PowerShell in Admin, Open the “Create_Users” script in PowerShell, but don’t run.
    
   ![Generate Bulk Users](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/a5dcf367-166a-42ca-948f-0091067f5c7d)

47.	  Type: Set-Execution \Policy Unrestricted in PowerShell to allow the run of scripts, press Enter. A dialog box will come up asking if you want to change the execution policy, click Yes to All. In PowerShell, navigate to the directory where the name.txt files are located (e.g., /desktop/AD_PS-master/). Now, click on the Create-Users script to ensure the window is enabled, select file -> Run, or click the green play button. A dialog box will ask if you want to run a script from the internet, select Run it Once, and allow the process to finish. (The password for all users is “Password1")

![Bulk Users PowerShell](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/14dab360-bc8e-4dce-9f74-a0c9f5e2cfd5)

![Confirmation of Bulk Users Added](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/0994ad82-3ad3-444b-9218-c7198610121e)
    
49.	Create a Windows 10 Virtual Machine: Select New Virtual Machine, create a desired name, select Windows 10 64-bit, increase RAM to 2GB, and Change Shared Clipboard/Drag’n’Drop to Bidirectional in the General/Advanced tab.
    
   ![Win10 Client Summary](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/5307a50c-c5e3-4832-994d-f0bc00f5402a)

51.	  In Network/Adapter 2, Select Enable Network Adapter, Change Attached to:” to Internal Network, assign the name to your liking. Click OK.
    
   ![Win10 Net  Setup](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/817623f1-5ab0-439d-89ac-22fbb28ef923)

53.	  Double-click the newly created client. A dialog box will open up to add the Win 10 ISO. Navigate to the directory of the Win 10 ISO. Select it, then click “Mount and Retry Boot.”
    
   ![Win10 Mount](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/7855cf13-b32a-4318-8bda-28a76f7786c8)

56.	  Select "I don’t have a Product Key." Select Win 10 Pro since Win Home does not have domain access. Click next. Select Custom Install. Select the desired drive if you have multiple drives. Click next. Click Install. After installation, select "Not to add a keyboard layout." Select Add Network later. Select "Add an offline account" (since we're not connected to a network or domain yet. Enter a username, skip adding a password, disable all privacy selections, click "skip/not now for remaining settings," and allow the process to finish.
    
![Win10 Version Selection](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/2b6bee86-aea5-4b25-bb3a-6bf8d237554a)

![Win10 Init](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/e60b0f54-5f80-4f19-9412-8f5bd2f991fc)
     
    ![Win10 Offline Account Setup](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/004ba529-359d-44cd-8668-15ff42758f4a)
56.	New Client Configuration/ Add New Client to Domain Controller: System, rename this PC (advanced), Click Change box, Rename computer name, Select “Domain” in Member Of, Type domain name (e.g., dhowardtech.com), click okay, enter domain username and password of dedicated domain account OR created user account in OU Admin (e.g., a-dthoward/password1!)
    
    ![Win10 Client Name Change   Add to Dom  Ctrlr](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/9a15b8b1-f22a-4026-9a1a-640921f470e4)

 ![Init  Win10 Client Added Confirmation](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/044b7198-e11e-41c0-9fa1-31a0df75ca23)
 
  ![Confirmation Win10 Added to Dom  Ctrlr](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/d336d555-a07a-4fd6-a50e-7da58be390b2)

   ![Successful New Admin Login](https://github.com/DHowardTech/Active_Directory_Lab/assets/166935576/10df1cc4-4964-49be-a434-2ab3aef0a85a)

58.	Finalize Active Directory Users and Computers
