# SOC-Simulated-Cyber-Attack-and-Log-Analysis-Lab
<p align="center">

![Screenshot 2024-10-06 095653](https://github.com/user-attachments/assets/022e791b-f0d6-4463-b5e2-d03d643fcace)


</p>

<h1>Logging and SecOps</h1>
In this lab, I simulate cyber attacks and perform log analysis in a Security Operations Center (SOC) scenario. First, I create a Windows VM outside the U.S. and simulate an attack from a designated "attack-vm." The attacker generates failed Remote Desktop Protocol (RDP), MS SQL authentication, and Secure Shell (SSH) logs by attempting to connect with incorrect credentials. As an admin, I then inspect these logs for failures and successes, analyzing EventIDs, source IPs, and other critical details in the Security and Application logs to identify and mitigate the attacks.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)
- SQL Server
- Linux

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1 - Create another Windows VM in a region outside the US and NAME IT “attack-vm”
- Step 2 - Attacker Mode, Generated some failed RDP logs against “windows-vm” (VM from previous lab)
- Step 3 - Generated some failed MS SQL Auth logs against “windows-vm”
- Step 4 - Generated some failed SSH logs against “linux-vm” (VM from previous lab)
- Step 5 - From your own computer, RDP back into “windows-vm”, Inspect the failures and successes (Security Log for RDP, Application Log for SQL), Take note of the EventIDs, messaging, Source IP Addresses, etc.
- Step 6 - SSH into the Linux VM, observe the logs with the following commands:cat /var/log/auth.log | grep password cat /var/log/auth.log | grep Accepted




<h2>Deployment and Configuration Steps</h2>

- Create another Windows VM in a region outside the US and NAME IT “attack-vm”
![Screenshot 2024-10-06 101310](https://github.com/user-attachments/assets/0190c23e-b846-4ee3-aa4b-6446f4dc519d)

- Attacker Mode,  Generated some failed RDP logs against “windows-vm” (VM from previous lab)
- From within of “attack-vm”, attempt to RDP into “windows-vm” with the wrong credentials
![Screenshot 2024-10-06 103646](https://github.com/user-attachments/assets/b331d5bc-36ee-4222-9db1-f3c2ceb4db86)

- Generated some failed MS SQL Auth logs against “windows-vm”
- Still within “attack-vm”, install SSMS if not already installed
- Attempt to connect to the SQL Server on “windows-vm” with a bad password

![Screenshot 2024-10-06 105922](https://github.com/user-attachments/assets/790f7be7-dd7d-4078-a638-4f4e13d2f3c8)

- Generated some failed SSH logs against “linux-vm”
- Still within “attack-vm”, attempt to SSH into “linux-vm” with the wrong credentials
- Log out of “attack-vm”, now you are back to your own computer
![Screenshot 2024-10-06 111334](https://github.com/user-attachments/assets/770fbdf6-10a6-404b-a031-15edb52794f6)

- From your own computer, RDP back into “windows-vm”
- Inspect the failures and successes (Security Log for RDP, Application Log for SQL)
- Take note of the EventIDs, messaging, Source IP Addresses, etc.
![Screenshot 2024-10-06 112741](https://github.com/user-attachments/assets/a1ef47b0-1344-48f2-abc7-c7e84aad6bfa)
![Screenshot 2024-10-06 113203](https://github.com/user-attachments/assets/175b0eed-df06-4e7e-a0d9-f1c3bc01192a)

- SSH into the Linux VM, observe the logs with the following commands: cat /var/log/auth.log | grep password           
![Screenshot 2024-10-06 114442](https://github.com/user-attachments/assets/b7c143b3-2535-4de5-837d-7b36c40fadba)
-  cat /var/log/auth.log | grep Accepted
![Screenshot 2024-10-06 114549](https://github.com/user-attachments/assets/c2395f4e-1ee1-477d-ae50-3b53d3163a1b)














