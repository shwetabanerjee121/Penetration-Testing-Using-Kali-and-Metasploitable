# Penetration-Testing-Using-Kali-and-Metasploitable

This repository documents a guided vulnerability assessment exercise using Metasploit, Kali Linux, and Metasploitable2, executed in an isolated virtual lab for ethical hacking training.

## Lab Setup

- Attacker VM: Kali Linux
- Target VM: Metasploitable2
- Environment: VMWare Workstation (host-only networking)

## Exploits Demonstrated

- `vsftpd_234_backdoor`: Remote code execution via malicious FTP server
- `samba/usermap_script`: Privilege escalation via reverse shell
- Post-exploitation: Created new UNIX user, confirmed `root` access

## Learning Outcomes

- Basic understanding of Metasploit modules
- Practice in controlled exploitation scenarios
- Insight into common service vulnerabilities and post-exploitation steps

## Screenshots

See the 'screenshots/' folder for:
- Shell access via Samba exploit
- FTP backdoor exploitation
- Root shell confirmation
- SSH login as a created backdoor user

## Disclaimer

All actions were performed in a controlled, offline environment using intentionally vulnerable machines. This repository is for educational purposes only.

Warning: Do NOT use these techniques outside of authorized penetration testing labs.

---

> Inspired by a Coursera Guided Project on Metasploit Basics 
> This project was independently reproduced and documented for educational use.
