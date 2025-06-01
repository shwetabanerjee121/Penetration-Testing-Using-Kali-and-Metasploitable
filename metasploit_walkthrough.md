# Metasploit Exploit Walkthrough

This markdown contains a detailed walkthrough of the steps taken during the Metasploit vulnerability assessment lab using Kali Linux and Metasploitable2.

---

## 1. Lab Setup

- Imported Kali Linux (attacker) and Metasploitable2 (target) into VMWare
- Set both VMs to host-only adapter mode
- Verified network connectivity using the following command from Kali:

  -> bash
      - ping 192.168.56.102

## 2. Scan and Identify Open Ports
  -> bash
      - nmap -sV 192.168.56.102 
      (This will show you available services (like FTP, Samba) on the target (Metasploitable2) VM.)
