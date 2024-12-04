# Wazuh Threat Hunting

Objective: To perform brute force attack on Windows 10 and Linux Ubuntu endpoints and monitor the authentication failure attempts on Wazuh Threat Hunting 

<h2>Configuration Steps</h2>

Attacker endpoint:
1.  Install Kali Linux on a VM 
2. Install the 'Hydra' tool 
  * Sudo apt-get update
  * Sudo apt-get install -y hydra
3. To perform attack emulation, run the following commands:
4. On Windows, we use RDP protocol 
 * <strong> sudo hydra -l <username> -p <password_list.txt>  rdp://<Windows_IP> </strong>
 
 ![image](https://github.com/user-attachments/assets/7ffc4816-a060-431d-9d49-4bbe3396dbbe)

5. On Linux, we use SSH  protocol 
* <strong>Sudo hydra -l <username> -p <password_list.txt>  < Linux_IP> ssh </strong>

<h2>Monitoring attack alerts on the Threat Hunting dashboard</h2> 

1. Navigate to the Threat Hunting module 
2. Use the following id filters to query the relevant alerts
   
* Linux: rule.id ( 5551 or 5712). Other related rules are 5710,5711,5716,5720,5503,5504 

![image](https://github.com/user-attachments/assets/2e13a1fe-62cf-41fe-a178-ea038dd2bb4f)

* Windows: rule.id (60122or 60204)

![image](https://github.com/user-attachments/assets/e6d8e056-1c8e-40ae-81f5-7e6c976f39ea)

