

Tags: [[incident_handling]] [[Cyber Security]] [[NIST]] [[htb]] [[jobrolepath]] [[SOC]] [[IT]] 
Date: 2024-10-09 15:41

---

## Source: 
[htb](https://academy.hackthebox.com/module/148/section/1363)

---

## Summary:


---

## Detailed Notes:
![[Cyber_kill_chain 1.png]]
- **Recon**
	-  This is the initial stage it involves information gathering. Some attackers use Instagram, Facebook, or job postings to collect information about the company they are targeting. Some companies put the tech stack they use on there job positing's. Attackers can use this to penetrate a company. 
- **Weaponize**
	- In this stage the attacker would prepare the Malware or payload to be sent to the organization. This could involve learning the firewall capabilities of a business as well as any EDR technology they may have. 
- **Deliver**
	-  This is when the exploit or payload is delivered. Attackers can deliver the exploit through emails, websites, or USB. Copying company websites are a good way to get a exploit inside of a organization. The websites look a lot like the websites the organizations use. Social engineering is another way attackers can get exploits into a organization. 
- **Exploit**
	- This is when the code or (exploit) is actually executed on the targets systems. 
- **Installation**
	-  Here is where the initial stager is executed, this could be with a [[Backdoor]]  , [[rootkit]], or a [[dropper]]. 
- **Command and Control**
	- In this stage the attack creates remote access to the target system. With this they are able to run command, and potentially pivot through the system. 
- **Action**
	- In the final stage of the Kill Chain the attacker will execute the actions they have compromised the system for. This could be exfiltrating data from the system, or it could be deploying [[ransomeware]]. 
  

---

---


