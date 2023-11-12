<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1> Active Directory Deployed in Azure</h1>
This tutorial outlines the implementation of Active Directory within Azure Virtual Machines.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- Microsoft Firewall 

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Generate Virtual machines within azure
- Install Active Directory on Domain Controller and create a domain
- Create new Organizational Unit within the Active Directory
- Create a new user and add to security group
- Log in to Domain Controller as new user
- Change client Virtual machine DNS to Domain controller's private IP address
- Join Client Virtual Machine to Domain
- Grant permission to non-administrative Domain users to access remote desktop
- Create additional users and log into Client Virtual Machine as one of the users 

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/xKa2jAv.png"/>
</p>
<p>
- Within Azure, create two Virtual Machines. The first Virtual Machine will be created using Windows Server 2022 and be the Domain Controller (DC-1). The second Virtual Machine will be created using Windows 10 and be the Client (Client-1).
</p>
<br />

<p>
<img src="https://i.imgur.com/37IXw8P.png"/>
</p>
<p> 
 - Within the Domain Controller, install Active Directory Domain Services. Create a new domain (reid.com) by promoting as a Domain Controller.  
</p>
<br />

<p>
<img src=https://i.imgur.com/YWX0xyA.png"/>
</p>
<p>
- Create new Organizationl Units within Active Directory (_EMPLOYEES AND _ADMINS). 
</p>
<br /> 

<p> 
<img src="https://i.imgur.com/4qtGCZ9.png"/>  
<p> 
<img src="https://i.imgur.com/Iarkokb.png"/> 
</p> 
<p> 
- Create a new user (Mickalia Reid) within Active Directory. Add new user to the security group (Domain Admins) so user can have access to Domain Controller as an Administrator. 
</p> 
<br /> 

<p> 
<img src="https://i.imgur.com/MujAORe.png"/> 
</p> 
<p> 
- Log in to Domain Controller as the new user. New user is now an Administrator of the Domain. 
</p> 
<br /> 

<p> 
<img src="https://i.imgur.com/v9u9hCM.png"/> 
</p> 
<p>  
- Within Azure, change the Client Virtual Machine's DNS settings to the Domain Controller's private IP address. 
</p> 
<br /> 

<p> 
<img src="https://i.imgur.com/ol9DjWZ.png"/> 
</p> 
<p> 
- Log into Client Virtual Machine as the administrator user created. Within Microsoft Firewall, change Client computer's domain to the Domain Controller (reid.com). Client Virtual Machine is now joined to Domain Controller and will now have access to the Active Directory as a user. 
</p>
<br /> 

<p> 
<img src="https://i.imgur.com/OmD5Nj7.png"/>  
<p> 
<img src=https://i.imgur.com/l9m3ZCO.png"/> 
</p> 
<p>
- Within the system properties on Client Virtual Machine, change the settings to allow other non-administrative users access to Client's remote desktop. All other non-administrative users registered on the Domain within Active Directory will now be able to access Client remote desktop. 
</p> 
<br /> 

<p> 
<img src="https://i.imgur.com/1orAcvT.png"/>  
<p> 
<img src="https://i.imgur.com/aFCCwRA.png"/> 
</p> 
<p> 
- Create additional users withinin the _EMPLOYEES foler in the Active Directory. Log into Client remote desktop as one of the other users created.

