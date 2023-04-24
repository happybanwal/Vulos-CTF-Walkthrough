# Vulos CTF Challenge Walkthrough

# Overview
In this write-up, I will be discussing my approach to solving the Vulos CTF challenge, which was based on network security. The challenge was given by my college, and I will explain the steps I took to solve it, including the tools and techniques I used along the way.

# Link
Machine link if you want to practice 🐱‍💻
[Dowload file from here](https://drive.google.com/file/d/1ZKe1PMH-Op4kEnpwLO185e7-50JeVBoo/view?usp=sharing)


# Steps
1. First, I googled the VM IP address, which was 192.168.56.3. It led me to an Apache server page, and upon inspecting the page, I found the username "TEST".

&nbsp;![Screenshot at 2023-04-24 03-27-05](https://user-images.githubusercontent.com/57853528/233869612-7053bcf9-bfe2-45e5-bafa-da7a64521c3a.png)

2. Next, I did an NMAP scan against 192.168.56.3 and found that SSH was running on port 22. However, when I tried connecting through SSH, I received a connection refused error. So, I scanned for all the ports, and I found Port 13652 was running.

&nbsp;![Screenshot at 2023-04-24 03-24-25](https://user-images.githubusercontent.com/57853528/233869521-604f892e-0e1b-423d-90a9-4b4c846a223d.png)


3. I tried to connect through SSH on port 13652, and it responded. Now, the quest for SSH password began. I ran a brute force attack with the help of Metasploit, and I found the password.

&nbsp;&nbsp;![Screenshot at 2023-04-24 04-05-14](https://user-images.githubusercontent.com/57853528/233869966-37aad4c1-bf5e-4b80-b367-8268ca642cd3.png)


4. I successfully got inside the machine, and I transferred the cap.pcapng file from the SSH server to my machine. Then, I analyzed it in Wireshark.

&nbsp;![Screenshot at 2023-04-24 05-20-17](https://user-images.githubusercontent.com/57853528/233874210-6a019e47-6da1-4267-8abc-541d3ed8a863.png)


5. On analysis, I found an FTP packet, and on the following packet, I found the ROOT password.

&nbsp;![Screenshot at 2023-04-24 05-25-27](https://user-images.githubusercontent.com/57853528/233874335-a8dfaf8c-2555-4652-a194-5f83696cbb17.png)

6. Now, I had the user "root" and password "5gr3ss9hvvc68mT66". After logging in as root, I found the flag in s3cr3t.txt. 😊

&nbsp;![Screenshot at 2023-04-24 05-26-54](https://user-images.githubusercontent.com/57853528/233874591-81800cbd-9a58-4fc5-8004-4676bf899846.png)


# Tools Used
Throughout the challenge, I used the following tools and techniques:
  * NMAP: for scanning the ports
  * Metasploit: for running a brute force attack
  * Wireshark: for analyzing the cap.pcapng file
  
  
# Conclusion
 In conclusion, the Vulos CTF challenge was an interesting exercise in network security.
 
