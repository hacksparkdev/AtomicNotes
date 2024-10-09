# {{Challenge Name}}

## Date: {{date}}

---

## Challenge Information:
- **Job Role**: (e.g., Penetration Tester, SOC Analyst)
- **Category**: (e.g., Exploitation, Enumeration, Network Security)
- **Platform**: Hack The Box
- **Challenge URL**: [Link](url)
- **Tools Used**: (List the tools you used to solve the challenge, e.g., Nmap, Metasploit, Hydra)

---

## Challenge Overview:
- A brief description of the challenge and what the main goal was (e.g., gaining root access, exploiting a vulnerability).

---

## Step-by-Step Process:
1. **Step 1**: Describe your initial reconnaissance or approach to solving the challenge.
   - Tools/Commands Used:
     ```bash
     nmap -sC -sV -oN scan.txt 10.10.10.10
     ```

2. **Step 2**: Walk through the exploitation or the process you used to solve the challenge.
   - Techniques and Commands Used:
     ```bash
     msfconsole
     ```

3. **Step 3**: Post-exploitation tasks (e.g., privilege escalation, loot collection).
   - Commands/Scripts Used:
     ```bash
     sudo -l
     ```

---

## Key Lessons Learned:
- **Lesson 1**: What new techniques or skills did you learn from this challenge?
- **Lesson 2**: Were there any difficulties you faced, and how did you overcome them?

---

## Tools/Commands Used:
- **Tool 1**: Description of how you used the tool (e.g., Nmap for port scanning).
- **Tool 2**: Command examples (if applicable):
   ```bash
   hydra -l admin -P /usr/share/wordlists/rockyou.txt 10.10.10.10 http-post-form "/login:username=^USER^&password=^PASS^:Invalid login"
