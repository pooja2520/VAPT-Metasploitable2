# VAPT-Metasploitable2
Vulnerability Assessment & Penetration Testing (VAPT) – Metasploitable 2

This project is a complete Vulnerability Assessment and Penetration Testing (VAPT) performed on Metasploitable 2, a purposely vulnerable Linux machine used for cybersecurity learning.
The assessment was executed from Kali Linux and includes scanning, enumeration, vulnerability detection, and evidence collection.

📁 Project Structure (Detailed Explanation)
VAPT-Metasploitable2/
│── README.md
│── nmap-scans/
│── enumeration/
│── screenshots/

✔ README.md

This file explains the project, tools used, commands executed, findings, and folder structure.

📂 nmap-scans/

This folder contains all Nmap scan result files. These are used to identify open ports, running services, OS details, and known vulnerabilities.

You should upload files such as:

nmap-syn-scan.txt
nmap-service-version.txt
nmap-os-detect.txt
nmap-vuln-scan.txt


Each file represents:

SYN Scan → Identify open ports stealthily

Service Detection → Check versions of services

OS Detection → Identify operating system

Vulnerability Scripts → Detect known service vulnerabilities

📂 enumeration/

This folder contains deeper analysis of services discovered by Nmap.

Upload files such as:

ftp-enum.txt
smb-enum.txt
nikto-scan.txt


These represent:

FTP Enumeration: Testing anonymous login

SMB Enumeration: Listing shares, users, OS info

Nikto Web Scan: Finding web server issues

Enumeration helps understand what attackers can access after discovering open ports.

📂 screenshots/

This folder contains all evidence of your practical work.
Screenshots show that you performed scanning and enumeration yourself.

Add images like:

ping-test.png

nmap-syn-scan.png

nmap-vuln-scan.png

ftp-anonymous-login.png

smb-enum4linux.png

nikto-output.png

Screenshots are very important for internship/project evaluation.

🛠 Tools Used
Tool	Purpose
Nmap	Port scanning, service detection, OS detection
Enum4Linux	SMB enumeration
Nikto	Web vulnerability scanning
FTP/Telnet Clients	Manual login testing
Kali Linux	Security testing OS
🔍 1. Information Gathering

Before scanning, check if the target is alive.

✔ Ping Command
ping -c 4 192.168.1.107


Expected result:

Host replies

Confirms network connectivity

🔎 2. Nmap Scanning (Detailed)

All scan results are stored in nmap-scans/.

✔ SYN Scan (Fast + Stealthy)
sudo nmap -sS 192.168.1.107 -oN nmap-scans/nmap-syn-scan.txt

✔ Service Version Detection
sudo nmap -sV 192.168.1.107 -oN nmap-scans/nmap-service-version.txt

✔ OS Detection
sudo nmap -O 192.168.1.107 -oN nmap-scans/nmap-os-detect.txt

✔ Vulnerability Scan
sudo nmap --script=vuln 192.168.1.107 -oN nmap-scans/nmap-vuln-scan.txt


You will discover services like:

FTP

SSH

Telnet

HTTP

SMB

MySQL

PostgreSQL

These help identify attack entry points.

📁 3. Service Enumeration (Detailed)

Results stored in enumeration/.

✔ FTP Enumeration
ftp 192.168.1.107


Try logging in:

Username: anonymous
Password: anonymous


If login is allowed → big security risk.

Save output as:

enumeration/ftp-enum.txt

✔ SMB Enumeration (Samba)
enum4linux -a 192.168.1.107 | tee enumeration/smb-enum.txt


Findings may include:

SMB version

Shared folders

Users

OS details

✔ Nikto Web Scan
nikto -h http://192.168.1.107 | tee enumeration/nikto-scan.txt


This identifies:

Outdated Apache

Directory listing

Misconfigurations

Possible vulnerabilities

📸 4. Screenshots

All practical proofs go here.
Examples:

ping result

Nmap output

Nikto scan

FTP login success

SMB enumeration

Your folder should look like:

screenshots/
│── ping-test.png
│── nmap-syn-scan.png
│── nmap-vuln-scan.png
│── ftp-login.png
│── smb-enum.png
│── nikto-scan.png

📝 5. Summary of Findings

Metasploitable 2 contains many insecure services such as:

Anonymous FTP

Telnet (plaintext password)

Outdated SMB

Outdated Apache

IRC backdoor

Vulnerable vsftpd

These allow attackers to gain system access.

🛡 6. Recommendations

Disable unused services

Patch outdated applications

Use SSH only (disable Telnet, FTP)

Install a firewall (UFW, iptables)

Strong password policies

Restrict network access

🎯 Conclusion

This VAPT project helped identify and analyze vulnerabilities in Metasploitable 2.
It demonstrates practical skills in:

Scanning

Enumeration

Vulnerability detection

Documentation
