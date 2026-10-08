Nmap is a scanning tool used by cyber security professionals to scan open ports, discover devices ,and vulnerabilities in computer systems.



I installed Nmap in system by this code:sudo dnf install nmap in my virtual machine and downloade it from nmap.org in windows.



then check ip addresses

ip a          # Linux

ipconfig      # Windows



Make a folder:

mkdir C:\\nmap\_project

cd C:\\nmap\_project





Run the scans:

For Host discovery:

nmap -sn 192.168.1.10



Quick scan (top 1000 ports):

nmap 192.168.1.10



Full TCP port scan:

sudo nmap -p- -T4 192.168.1.10 -oN full\_ports.txt



Service and version detection:

sudo nmap -sV -p 22,80,443 192.168.1.10 -oN services.txt



OS detection:

sudo nmap -O 192.168.1.10 os.txt



Default scripts:

Nmap -sC -sV -p 21,22,80 <IP> -oN 4\_scripts.txt



Vulnerability scripts:

sudo nmap -sC -sV --script vuln -p 22,80,443 192.168.1.10 -oN vuln\_scan.txt



Before hardening:

nmap -A -p- <IP> -oA before\_hardening







NOW HARDEN AND RESCAN:(ON CentOS)

sudo systemctl disable --now vsftpd

sudo firewall-cmd --permanent --remove-service=ftp

sudo firewall-cmd --reload



(On Windows)



nmap -A -p- <IP> -oA after\_hardening

