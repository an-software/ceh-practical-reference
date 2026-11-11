# Overview of Important Standard Network Ports

Here is an overview of the most important standard network ports in a clear Markdown table.

## Port Ranges (IANA)

| Type | Range | Description |
| --- | --- | --- |
| Well-Known Ports | 0–1023 | Fixed standard services (e.g., HTTP, SSH, FTP). |
| Registered Ports | 1024–49151 | User applications or third-party services. |
| Dynamic / Ephemeral Ports | 49152–65535 | Temporary connections used by clients. |

## Commonly Used Standard Ports

| Port | Protocol | TCP/UDP | Description |
| --- | --- | --- | --- |
| 20 / 21 | FTP | TCP | File transfer (unencrypted) |
| 22 | SSH / SFTP | TCP | Secure remote administration |
| 23 | Telnet | TCP | Unencrypted terminal connection |
| 25 | SMTP | TCP | Email transmission between servers |
| 53 | DNS | TCP / UDP | Name resolution (domain ↔ IP address) |
| 67 / 68 | DHCP | UDP | Automatic IP address assignment |
| 80 | HTTP | TCP | Unencrypted web traffic |
| 110 | POP3 | TCP | Email retrieval |
| 123 | NTP | UDP | Time synchronization |
| 143 | IMAP | TCP | Email synchronization |
| 389 | LDAP | TCP / UDP | Directory service (unencrypted) |
| 443 | HTTPS | TCP | Encrypted web traffic (SSL/TLS) |
| 445 | SMB | TCP | Windows file sharing |
| 465 / 587 | SMTPS / Submission | TCP | Secure email transmission |
| 636 | LDAPS | TCP | LDAP over SSL/TLS |
| 993 | IMAPS | TCP | Encrypted IMAP |
| 995 | POP3S | TCP | Encrypted POP3 |
| 1433 | MSSQL | TCP | Microsoft SQL Server |
| 3306 | MySQL / MariaDB | TCP | MySQL database service |
| 3389 | RDP | TCP | Windows Remote Desktop |
| 5432 | PostgreSQL | TCP | PostgreSQL database service |
| 8080 | HTTP-Alt | TCP | Alternative HTTP port / proxy / Tomcat |
