

Tags: [[Cyber Security]]  [[cyber_kill_chain]] [[incident_handling]] [[NIST]] 

Date: 2024-10-09 17:04

---

## Source: 


---

## Summary:
A backdoor is any method that allows unauthorized access to a system, bypassing normal authentication mechanisms. Attacker will use these backdoors to gain ongoing access to a compromised system. 

---

## Detailed Notes:
- **How Backdoors are Exploited in Cybersecurity:**
	- **Persistence**: Backdoors are often used to maintain long-term access without the need for constant re-exploitation of vulnerabilities.
	- **Stealth**: Backdoors are designed to operate quietly in the background, avoiding detection by security software or system administrators.
	- **Privilege Escalation**: Attackers may use a backdoor to escalate their privileges, gaining administrative access to a system.
	- **Exfiltration**: Once a backdoor is established, attackers can extract sensitive data or files without the victim knowing.

---
### **Examples of Backdoors** 

- **Netcat Backdoor**:
    
    - Netcat is a legitimate networking tool used for reading from and writing to network connections. Attackers often misuse it to create a backdoor by establishing a reverse shell, allowing them to remotely control the compromised system.
    - Example: An attacker installs Netcat on a target machine and configures it to listen on a port, enabling them to connect and control the system remotely whenever needed.
- **Back Orifice**:
    
    - A well-known backdoor tool that was popular in the 1990s. It allows remote administration of a Windows machine and can perform actions like capturing keystrokes or transferring files.
    - Example: Once installed, it provides the attacker with continuous access to the compromised machine without alerting the user.
- **Remote Access Trojan (RAT)**:
    
    - A RAT is malware that provides the attacker with remote control over the victim's system. Some well-known RATs include DarkComet, njRAT, and Poison Ivy.
    - Example: A RAT allows attackers to monitor user activities, steal credentials, capture screenshots, and manipulate files without the user's knowledge.
- **Hidden SSH Service**:
    
    - Attackers may install an unauthorized SSH service on a Linux server, which remains hidden from system administrators, allowing them to connect via SSH and gain full access.
    - Example: The attacker creates a second SSH service running on an obscure port to avoid detection and maintain access to the system.
- **Firmware Backdoor**:
    
    - Backdoors can also be introduced into a device's firmware, enabling the attacker to control the hardware at a low level. This type of backdoor is hard to detect and remove.
    - Example: A compromised router or IoT device firmware might allow the attacker to intercept network traffic or launch attacks on other connected devices.
---


