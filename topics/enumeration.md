# Enumeration

Keywords: SMB SNMP shares banners services anonymous access.

Identify services, then inspect metadata and access using lab credentials. Prefer focused checks.

```bash
nmap -sT -sV -p 21,22,80,139,445 192.0.2.10
smbclient -L //192.0.2.10 -U labuser
# Anonymous listing only within lab scope:
smbclient -L //192.0.2.10 -N
# Replace community with the lab-supplied value:
snmpwalk -v2c -c lab-community 192.0.2.10 1.3.6.1.2.1.1
curl -I http://192.0.2.10/
```

Tools in this example: [curl](../tools/curl.md), [Nmap](../tools/nmap.md), [smbclient](../tools/smbclient.md), [snmpwalk](../tools/snmpwalk.md).

Record share names, actual access levels, versions and exposed metadata. A discovered share is not necessarily readable or writable. Anonymous denial is useful evidence.

Troubleshooting: distinguish connectivity from authentication failures. Verify domain/workgroup and username format. SNMPv3 requires matching authentication/privacy settings. Avoid enabling legacy SMB protocols indiscriminately to work around negotiation failures.

Sources: [Nmap](https://github.com/nmap/nmap), [HackTricks](https://github.com/HackTricks-wiki/hacktricks), [smbclient manual](https://www.samba.org/samba/docs/current/man-html/smbclient.1.html).

## Service and domain checklist

| Port | Typical service; confirm by probing |
| --- | --- |
| 21/TCP | FTP control; 20/TCP is traditional active-mode FTP data |
| 22/TCP, 23/TCP | SSH, Telnet |
| 25/TCP, 110/TCP, 143/TCP | SMTP, POP3, IMAP |
| 53/UDP and TCP | DNS |
| 80/TCP, 443/TCP, 8080/TCP | Common HTTP/HTTPS or alternate web ports |
| 135/TCP, 139/TCP, 445/TCP | MS RPC endpoint mapper, NetBIOS session, direct SMB |
| 161/UDP | SNMP |
| 1433/TCP, 3306/TCP | Typical MSSQL, MySQL |
| 3389/TCP | RDP; not 3386 |

```bash
enum4linux -a 192.0.2.10
rpcclient -U labuser 192.0.2.10 -c 'querydominfo; enumdomusers'
# Follow discovery with a narrow service check:
sudo nmap -sU -p 161 -sV 192.0.2.10
```

Tools in this example: [enum4linux](../tools/enum4linux.md), [Nmap](../tools/nmap.md), [rpcclient](../tools/rpcclient.md).

Windows command tools (run inside the authorized Windows session):

```powershell
nbtstat -A 192.0.2.10
nbtstat -c
net use
net user
net user /domain
net user labuser /domain
Get-CimInstance Win32_UserAccount | Select-Object Name,Domain,SID
```

Tools in this example: [nbtstat](../tools/nbtstat.md), [Windows net commands](../tools/net.md).

[`nbtstat -A`](../tools/nbtstat.md) takes an IP; lowercase `-a` takes a remote name. [`netstat`](../tools/netstat.md) reports local connections, not arbitrary remote NetBIOS users. [`snmp-check`](../tools/snmp-check.md) enumerates SNMP data, not NetBIOS. [`net user /domain`](../tools/net.md) depends on a reachable domain controller and the current security context.

For authenticated FTP retrieval, open [`ftp 192.0.2.10`](../tools/ftp.md), log in when prompted, inspect `pwd`/`ls`, use `binary` for binary data, then `get lab-file.txt` and `bye`. If listing works but transfer fails, check file permissions and active/passive data-channel routing; do not assume a successful login grants every file.
