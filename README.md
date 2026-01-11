# Deploying-Active-Directory
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This is a demonstration of me using Active Directory. I created two virtual machines. One is for an admin, and the other is for clients/employees in a workspace. <br />
<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)


<h2>Microsoft Azure Set Up</h2>

Within Microsoft Azure, I first created a resource group for the grouping of my virtual machines and networks.
![EC48B006-94E9-414E-84D1-DF50DA2327E3_1_201_a](https://github.com/user-attachments/assets/eceab6cd-8460-44e2-a638-5f69a6c96637)

I then created my virtual network.An Azure Virtual Network is a private, isolated cloud network that serves as the foundation for secure communication between Azure resources such as virtual machines, databases, and applications, while also enabling connectivity to on-premises networks. 
![2DE04152-F672-44F1-92E6-2919D6944A80_1_201_a](https://github.com/user-attachments/assets/4c0f5237-8bb5-415e-815d-2087d2758c24)

Next I created two virtual machines within the resource group. Client 1 and DC-1 (Domain Controller). 
![F126DE4B-471A-49E5-BEE3-0DC602F26569_1_105_c](https://github.com/user-attachments/assets/9e312aa3-bb4d-4340-867b-f494a5ab6130)

I changed the IP address of my domain controller VM from dynamic to static. This ensured that it will have the same private IP address throught the lab. 
<img width="3024" height="1964" alt="3B3DAACD-BFD9-467A-A397-0D81F894F478" src="https://github.com/user-attachments/assets/d4edf829-a075-4332-99b3-98c2d131c7a4" />
<img width="3024" height="1964" alt="28485E55-1BFF-4779-8EC1-530D8AE83B72" src="https://github.com/user-attachments/assets/4b914116-b477-4fba-a208-c96c2234bc42" />

I was then able to change the Client VM's DNS server to the Domain VM IP address. I did this by changing it from inheriting it's own DNS server to using the static IP address that the Domain VM now has.
<img width="3024" height="1964" alt="6BA74D52-774D-454C-A760-BE6F0C087359" src="https://github.com/user-attachments/assets/e9afe5c7-54d7-4ea3-90b7-1c305194e782" />
<img width="3024" height="1964" alt="6C8D8C2D-14BB-49BF-A72C-5A977A24A735" src="https://github.com/user-attachments/assets/0c33988e-0d6c-466a-ae10-0181e23b4a4e" />

As of now, the two VMs were essentially just computers. Outside of the seignated names of the VMs, there wasn't anything special about them. This is when I begin to set up the Domain Controller VM. 

I first had to add the Active Directory feature to the VM. I did this by adding roles and features. I then was able to check off "Active Directory and Domain Services." 
<img width="1512" height="982" alt="EFF6A13D-5705-49FB-AAA8-0E82917C4324" src="https://github.com/user-attachments/assets/9204c040-09a0-440e-9597-58598bbad85d" />
<img width="1512" height="982" alt="DDF8950F-6504-4564-AB93-BA6B8772C0C2" src="https://github.com/user-attachments/assets/18817905-729e-4627-8f56-89d954a5139c" />
<img width="1512" height="982" alt="9EA2F8ED-6B55-4FBC-8A41-4657B878E720" src="https://github.com/user-attachments/assets/55a3db42-208e-477a-b67a-18a1ca681119" />

This allowed me to configure the domain I will be working from. I added a new forest as Mydomain.com 
![5FA7F2CB-01BA-41A5-8F90-85DB361685DD_1_105_c](https://github.com/user-attachments/assets/2614b478-311b-490b-8a99-ab21e5c241a7) 

I created a new organizational group for employees that will be used later. 
This is where all of the employees' information will be held once added.  
![FBB40A33-4A23-47EC-AE74-4BDB75A88450_1_201_a](https://github.com/user-attachments/assets/c738b343-d5a5-4642-a7d5-81edb012b840)

Next, I created a separate organizational group for admins.
![24A51FC2-F636-4093-9980-E684EBFB3111_1_201_a](https://github.com/user-attachments/assets/9ae4231c-feaf-4ee0-b1f9-8e31380151dc)

The Admin's role was vacant, so I began to create my admin.
![14D99E6D-D113-4515-8E06-94AD473E95E6_1_105_c](https://github.com/user-attachments/assets/d154cbf5-454f-49ef-8f3e-a7b2b50ee970)

I created the admin Jane Doe. This required her credentials and a username
![6118E0D7-8A0A-49AB-945A-50956115D41C_1_105_c](https://github.com/user-attachments/assets/38839d57-4847-4c91-8e9c-628ed7d48a64)
![C468821E-1104-4735-99C2-203DCCEFF7CD_1_201_a](https://github.com/user-attachments/assets/409ea321-89b7-451c-87fa-c08562606702)

Now with an admin, I had the access to the client VM to the domain. 
![C545DF53-2D1A-4095-B88E-EA9A94E19F52_1_105_c](https://github.com/user-attachments/assets/ba2772be-53e5-483a-8cd0-80496f9acd28)
<img width="1512" height="982" alt="485EED98-BC98-4D94-878C-9241C9A134D5" src="https://github.com/user-attachments/assets/b0c41807-d755-49f9-b2aa-a890a569b410" />
![D6832A57-42EE-4472-89D7-58D4AFAF1B77_1_201_a](https://github.com/user-attachments/assets/a4a93e3b-0b9b-49dc-b33e-67891f105304)
![17F5941A-EB8D-451D-84E6-0B2F2BE4743B_1_105_c](https://github.com/user-attachments/assets/fc93c043-2891-43c2-99ca-3b7c41d64e74)














<h2>Admin account</h2>

I created an admin account under the credentials Jane Doe. This allowed me to simulate common acts in IT such as 
- Password resets
- Account locking
- Account enabling
- changing account policies
  <img width="1512" height="982" alt="BCA7A6DE-E9F2-4DA4-983B-1BF3C0D848D6" src="https://github.com/user-attachments/assets/a00b513e-edd2-4e02-9571-b88ca883f3e2" />
 
<h2>Domain Policies</h2>
As the admin, I had to establish domain policies similar to what real-world companies follow. This included failsafes such as 

- Account lockout duration
- Account lockout threshold

  <img width="1512" height="982" alt="EF878B4F-EA59-4CC1-A014-1802C4CD250A" src="https://github.com/user-attachments/assets/88da02ff-89ad-43fe-b47a-4212e1422eaf" />
  <img width="1512" height="982" alt="6A8DC3C4-7A25-407F-AD14-5EEAADE4133D" src="https://github.com/user-attachments/assets/73aed088-efc3-4fd0-b98f-9a87b25aa37b" />
  <img width="1512" height="982" alt="E5ADD679-160F-4AF8-BC2C-083D556521E1" src="https://github.com/user-attachments/assets/5dcb0cf0-fe72-4ccb-a64a-7c1172be6a4c" />
  <img width="1512" height="982" alt="2A8F4D06-C880-4C36-8F25-D9D3A5A1CD95" src="https://github.com/user-attachments/assets/4b42195e-41d1-404a-bfb4-c79707405b2e" />




<h2>Password reset </h2>
As an employee, I simulated what would happen if you guess the password incorrectly too many times. This resulted in the user's account being locked.

![96F0FB0C-E063-4815-A547-4DCF9C81F452_1_201_a](https://github.com/user-attachments/assets/6a0ed9e1-0f36-49f3-839c-171fa7b50d1a)

After 5 attempts, the user's account was locked. This is where the admin has to unlock the user's account and possibly reset the password.
<img width="1512" height="982" alt="E2336BBE-9191-4C65-8969-15ABCE6D25D3" src="https://github.com/user-attachments/assets/8f236e74-254f-4070-8faa-68bf37f0cbff" />
<img width="1512" height="982" alt="D0AFB8BA-AF2A-42B1-A4A3-24FD065D6F39" src="https://github.com/user-attachments/assets/bbe13015-53f3-4a72-884a-1f45719f771c" />





<h2>Account Reanabling</h2>

There are many instances of why an account might need to be disabled and enabled. I tried to log into an user that was recently disabled by the admin. I was then prompted with a message saying that the account was disabled and the user wasnt able to log in. 
<img width="1512" height="982" alt="FA199A3B-0B45-4AE0-8AE9-B52C2B8E12E5" src="https://github.com/user-attachments/assets/782273f1-bfbf-4b04-a4e9-75e834dca418" />

![72194312-6A08-4AF5-87F6-01C2523AE6F7_1_201_a](https://github.com/user-attachments/assets/255b78e8-f339-45d8-a23c-c1d8fe4f4571)

As the admin I then had to reenable the account.



