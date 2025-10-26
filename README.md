# Deploying-Active-Directory
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This is a demonstration of me using Active Directory. I created two virtual machines. One is for an admin and the other is for clients/employees in a workspace. <br />
<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Admin account</h2>

I created an admin account under the credentials Jane Doe. This allowed me to simulate common acts in IT such as 
- Password resets
- Account locking
- Account enabling
- changing account policies
  <img width="1512" height="982" alt="BCA7A6DE-E9F2-4DA4-983B-1BF3C0D848D6" src="https://github.com/user-attachments/assets/a00b513e-edd2-4e02-9571-b88ca883f3e2" />
 
<h2>Domain Policies</h2>
As the admin, I had to establish domain polocies similar to what real world companies follow. This included failsafes such as 

- Account lockout duration
- Account lockout threshhold

  <img width="1512" height="982" alt="EF878B4F-EA59-4CC1-A014-1802C4CD250A" src="https://github.com/user-attachments/assets/88da02ff-89ad-43fe-b47a-4212e1422eaf" />
  <img width="1512" height="982" alt="6A8DC3C4-7A25-407F-AD14-5EEAADE4133D" src="https://github.com/user-attachments/assets/73aed088-efc3-4fd0-b98f-9a87b25aa37b" />
  <img width="1512" height="982" alt="E5ADD679-160F-4AF8-BC2C-083D556521E1" src="https://github.com/user-attachments/assets/5dcb0cf0-fe72-4ccb-a64a-7c1172be6a4c" />
  <img width="1512" height="982" alt="2A8F4D06-C880-4C36-8F25-D9D3A5A1CD95" src="https://github.com/user-attachments/assets/4b42195e-41d1-404a-bfb4-c79707405b2e" />




<h2>Password reset </h2>
As an employee, i simulated what would happen if you guess the password incorrectly too many times. This resulted in the users account being locked.

![96F0FB0C-E063-4815-A547-4DCF9C81F452_1_201_a](https://github.com/user-attachments/assets/6a0ed9e1-0f36-49f3-839c-171fa7b50d1a)

After 5 attempts, the users account was locked. This is where the admin has to unlock the users account and possibly reset the password.
<img width="1512" height="982" alt="E2336BBE-9191-4C65-8969-15ABCE6D25D3" src="https://github.com/user-attachments/assets/8f236e74-254f-4070-8faa-68bf37f0cbff" />
<img width="1512" height="982" alt="D0AFB8BA-AF2A-42B1-A4A3-24FD065D6F39" src="https://github.com/user-attachments/assets/bbe13015-53f3-4a72-884a-1f45719f771c" />





<h2>Account Reanabling</h2>

There are many instances on why an account might need to be disabled and enabled. I tried to log into an user that was recently disabled by the admin. I was then prompted with a message saying that the account was disabled and the user wasnt able to log in. 
<img width="1512" height="982" alt="FA199A3B-0B45-4AE0-8AE9-B52C2B8E12E5" src="https://github.com/user-attachments/assets/782273f1-bfbf-4b04-a4e9-75e834dca418" />

![72194312-6A08-4AF5-87F6-01C2523AE6F7_1_201_a](https://github.com/user-attachments/assets/255b78e8-f339-45d8-a23c-c1d8fe4f4571)

As the admin I then had to reanable the account.


<h2>Active Directory conclusion</h2>
An admin account is very important for any company. An admin can have control over thousands of accounts across a network. This is a nessecity. we went over

- Password resets
- Account locking
- Account enabling
- changing account policies

 This is just a small amount of what active directory can do. There is many other possibilities as you change the domain polices 

