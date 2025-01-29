<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- IIS
- PHP Manager
- Rewrite Module
- VC_redistx86
- MySQL 5.5.62
- Heidi SQL

<h2>Installation Steps</h2>

Create a Virtual Machine in Azure. Type osTicket for Resource Group 

       ![Screenshot 2025-01-27 072414](https://github.com/user-attachments/assets/6d48998f-9fbd-4869-b01b-921c8ade3f4a)
       ![Screenshot 2025-01-27 072911](https://github.com/user-attachments/assets/96fe0962-1a83-4e84-91a8-f4120b6ae31b)


For image: Windows 10       
For size: any compatible 2 vcpus, 8 GiB memory is recommended

![Screenshot 2025-01-27 073445](https://github.com/user-attachments/assets/5eaf29d8-e520-4462-90c3-9506550404c4)


Add username and password  and check licensing agreement and click create 

![Screenshot 2025-01-27 073607](https://github.com/user-attachments/assets/ea334450-56f8-4842-aa9f-50da837b8c97)
![Screenshot 2025-01-27 073816](https://github.com/user-attachments/assets/ac6f16da-175b-424b-970a-2ec84aaa4dc1)






Log into VM on Remote Desktop using VM public ip address 

![Screenshot 2025-01-27 074738](https://github.com/user-attachments/assets/d201766d-5766-4cf3-8149-799e5f3aafcd)



Within VM, download osTicket installation zip file and open file location 

![Screenshot 2025-01-27 080159](https://github.com/user-attachments/assets/7c2b379c-6490-451d-b539-8c772c62fb8c)



From location move file to desktop and extract all 

![Screenshot 2025-01-27 080920](https://github.com/user-attachments/assets/acb42454-f78f-4054-97e5-d6f69904ac29)


Enable IIS in windows with CGI
 - Go to control panel, programs, click turn windows features on or off, check Internet Information Services and expand the folder. Under Worldwide Web services, check CGI and click ok
   
   ![Screenshot 2025-01-27 081348](https://github.com/user-attachments/assets/fa260883-0281-4002-aa1d-61d6a0825169)

Install PHP manager 
 - From osTicket installation file select and install PHP manager
   
   ![Screenshot 2025-01-27 082253](https://github.com/user-attachments/assets/bc77c7ca-6c59-4008-877d-59cc0f0a2ac4)


Install Rewrite Module 
 - from osTicket installation files, select and install Rewite module
   
   ![Screenshot 2025-01-27 082423](https://github.com/user-attachments/assets/0cc457a1-7bf3-4fc0-9b0b-0c6acb0054c6)

   
Create the directory C:\PHP

 ![Screenshot 2025-01-27 082837](https://github.com/user-attachments/assets/60681bd5-c36b-4719-a070-61a95718899a)



Extract PHP folder from installation files to PHP folder in C directory 

  ![Screenshot 2025-01-27 083442](https://github.com/user-attachments/assets/ac2fb743-7ba2-4e5e-82d5-5019a9d8e897)



Install VC_redist.x86.exe.

  ![Screenshot 2025-01-27 083703](https://github.com/user-attachments/assets/dd7c9429-73cb-4880-9d1c-43362d1bf7cf)


Install MySQL 

  ![Screenshot 2025-01-27 083739](https://github.com/user-attachments/assets/101b5bb6-3ae7-4d6a-aba0-960483767476)


Open IIS as an admin 

![Screenshot 2025-01-27 084214](https://github.com/user-attachments/assets/bac92bde-08eb-47b3-ab71-fdaf2c2f1529)


   

register PHP from within IIS  and then reload IIS 

   ![Screenshot 2025-01-27 084614](https://github.com/user-attachments/assets/34c8552e-b471-4969-a629-9deb19661425)
   ![Screenshot 2025-01-27 084635](https://github.com/user-attachments/assets/79bd60ef-507a-420b-835e-841aa5146a4f)


Install osTicket from osTicket installation files 
  - Unzip and copy upload folder into =.  c:\inetpub\root and rename it as  osTicket 
  - Open browse osTicket in IIS
    
     ![Screenshot 2025-01-27 085228](https://github.com/user-attachments/assets/feb7dd9d-4064-4078-aba7-600f13d63b69)
     ![Screenshot 2025-01-27 092242](https://github.com/user-attachments/assets/c5c37727-8d9a-42d5-86b7-cc6edfa0f715)


  - Sites, default web site, osTicket, browse
    
    ![Screenshot 2025-01-27 093009](https://github.com/user-attachments/assets/593c8004-ae31-495b-895b-f4c9bd6e9324)
    ![Screenshot 2025-01-27 093031](https://github.com/user-attachments/assets/d20d0476-74f7-40b0-b651-4ac8eec0dd3a)

Rename ost-config.php 

   ![Screenshot 2025-01-27 102823](https://github.com/user-attachments/assets/547870e5-1d10-4172-8f7a-7832ea8468e1)

   

Assign Permissions: ost-config.php
 - Disable inheritance -> Remove All
 - New Permissions -> Everyone -> All
   
   ![Screenshot 2025-01-27 103056](https://github.com/user-attachments/assets/ca3472cc-9e88-4393-a217-548f968b50f4)
   ![Screenshot 2025-01-27 103228](https://github.com/user-attachments/assets/7535dd88-c125-4f17-89b2-cdc1b3b42c4f)
   ![Screenshot 2025-01-27 103401](https://github.com/user-attachments/assets/0c8e3a94-e0bf-496b-a4b5-d619645aa03a)

 

Back on osTicket website click continue and fill out installation form 

  ![Screenshot 2025-01-27 103616](https://github.com/user-attachments/assets/0f1607a0-59e9-4ccc-8c59-4c366f394031)


Install heidiSQL and setup database for osTicket to use
 - From the “osTicket-Installation-Files” folder, install HeidiSQL.
 - Open Heidi SQL
 - Create a new session, root/root
 - Connect to the session
 - Create a database called “osTicket”
   
   ![Screenshot 2025-01-27 104157](https://github.com/user-attachments/assets/d27e24cd-3e3d-422d-a43d-c2c2ace5229b)
   ![Screenshot 2025-01-27 104449](https://github.com/user-attachments/assets/f30d9724-3c72-42b6-b1ff-6cbf8e556c9b)
   ![Screenshot 2025-01-27 104544](https://github.com/user-attachments/assets/d32d83fd-6ffd-4d0f-8ff3-d224bfdde63a)
   ![Screenshot 2025-01-27 104753](https://github.com/user-attachments/assets/bd3f6467-0f5d-4095-ace8-69faad72c772)


And osTicket is installed!

  ![Screenshot 2025-01-27 104918](https://github.com/user-attachments/assets/341084e4-507b-45e3-85e3-0bc0b88f7832)
 

Thank you for viewing! I hope you enjoyed it as much as did setting it up!

