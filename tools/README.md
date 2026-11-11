# Tool reference index

One Markdown file per named tool/service or separately useful suite component. The 18 entries from the latest supplied writeup come first; the remaining entries cover named tools, datasets, frameworks and key command utilities in the earlier topic/domain/source notes. Aliases and spelling variants share a page. Ordinary shell file-management/filtering commands, generic product categories and training sites are not treated as separate security tools.

This is documentation only: nothing is installed, submitted to a service or executed. Commands use synthetic names and reserved documentation addresses; run them only in an authorized lab with the appropriate OS/tool installed. Keep evidence and secret material outside Git. All indexed entries are recorded in [catalog.json](catalog.json).

The latest writeup's URL/author was not supplied, so its provenance is recorded only as the user-provided excerpt in this chat. It prioritizes [OpenVAS](openvas.md) and [Hashes.com](hashes-com.md) alongside the other listed tools. Hash recovery is not message decryption; [SNOW](snow.md) extracts text whitespace while [OpenStego](openstego.md) handles its compatible image data. CVE identifiers describe particular cataloged vulnerabilities; CWE describes weakness types.

## Priority writeup tools

| Tool | Main use |
| --- | --- |
| [Nmap](nmap.md) | Discovery |
| [Hydra](hydra.md) | Passwords |
| [sqlmap](sqlmap.md) | Web testing |
| [John the Ripper](john.md) | Passwords |
| [Hashcat](hashcat.md) | Passwords |
| [Metasploit Framework](metasploit.md) | Privilege escalation |
| [Wireshark](wireshark.md) | Forensics |
| [Steghide](steghide.md) | Forensics |
| [OpenStego](openstego.md) | Forensics |
| [SNOW](snow.md) | Forensics |
| [SearchSploit](searchsploit.md) | Vulnerability assessment |
| [Aircrack-ng](aircrack-ng.md) | Wireless |
| [VeraCrypt](veracrypt.md) | Cryptography |
| [HashCalc](hashcalc.md) | Cryptography |
| [OWASP ZAP](owasp-zap.md) | Web testing |
| [OpenVAS / Greenbone](openvas.md) | Vulnerability assessment |
| [PhoneSploit](phonesploit.md) | Mobile and cloud |
| [Hashes.com](hashes-com.md) | Passwords |

## Earlier repository tools

### Cryptography

- [BCTextEncoder](bctextencoder.md)
- [CrypTool](cryptool.md)
- [Get-FileHash](get-filehash.md)
- [HashMyFiles](hashmyfiles.md)
- [MD5 & SHA-1 Checksum Utility](md5-sha1-checksum-utility.md)
- [md5sum](md5sum.md)
- [OpenSSL](openssl.md)
- [sha256sum](sha256sum.md)

### Discovery

- [dig](dig.md)
- [getent](getent.md)
- [ip (iproute2)](ip.md)
- [Masscan](masscan.md)
- [Netdiscover](netdiscover.md)
- [nslookup](nslookup.md)
- [Unicornscan](unicornscan.md)
- [Zenmap](zenmap.md)

### Enumeration

- [Dcomcnfg / Component Services](dcomcnfg.md)
- [enum4linux](enum4linux.md)
- [FTP client](ftp.md)
- [Gacutil](gacutil.md)
- [MySQL client](mysql.md)
- [nbtstat](nbtstat.md)
- [netstat](netstat.md)
- [OleView](oleview.md)
- [rpcclient](rpcclient.md)
- [RpcDump](rpcdump.md)
- [smbclient](smbclient.md)
- [smbmap](smbmap.md)
- [snmp-check](snmp-check.md)
- [snmpwalk](snmpwalk.md)
- [UserEnum](userenum.md)
- [Windows net commands](net.md)

### Forensics

- [Autopsy](autopsy.md)
- [binwalk](binwalk.md)
- [capinfos](capinfos.md)
- [Covert_TCP](covert-tcp.md)
- [Cuckoo Sandbox](cuckoo.md)
- [Dependency Walker](dependency-walker.md)
- [ExifTool](exiftool.md)
- [file](file.md)
- [FireEye analysis platform reference](fireeye.md)
- [FTK Imager](ftk-imager.md)
- [GDB](gdb.md)
- [Ghidra](ghidra.md)
- [hexdump](hexdump.md)
- [IDA](ida.md)
- [Joe Sandbox](joe-sandbox.md)
- [Malwoverview](malwoverview.md)
- [Mandiant Redline](redline.md)
- [objdump](objdump.md)
- [OllyDbg](ollydbg.md)
- [PEiD](peid.md)
- [PEStudio](pestudio.md)
- [PEview](peview.md)
- [Process Monitor / ProcMon](procmon.md)
- [QuickStego](quickstego.md)
- [radare2](radare2.md)
- [readelf](readelf.md)
- [Regshot](regshot.md)
- [sandfly-entropyscan](sandfly-entropyscan.md)
- [Stegseek](stegseek.md)
- [strace](strace.md)
- [strings](strings.md)
- [tcpdump](tcpdump.md)
- [The Sleuth Kit](sleuth-kit.md)
- [tshark](tshark.md)
- [VirusTotal](virustotal.md)
- [Volatility 3](volatility.md)
- [WinDbg](windbg.md)
- [YARA](yara.md)
- [zsteg](zsteg.md)

### Historical SQL tools

- [BBQSQL](bbqsql.md)
- [Blisqy](blisqy.md)
- [Havij](havij.md)
- [jSQL Injection](jsql-injection.md)
- [MyBatis](mybatis.md)
- [NoSQLMap](nosqlmap.md)
- [SQLiX](sqlix.md)
- [SQLNinja](sqlninja.md)
- [SQLSentinel](sqlsentinel.md)

### Mobile and cloud

- [Android Debug Bridge (adb)](adb.md)
- [Android Studio emulator](android-studio.md)
- [Apktool](apktool.md)
- [AWS CLI](aws-cli.md)
- [Azure CLI (az)](azure-cli.md)
- [Google Cloud CLI (gcloud)](gcloud.md)
- [JADX](jadx.md)
- [Remote Desktop / RDP client](rdp.md)
- [WinSCP](winscp.md)

### Passwords

- [CeWL](cewl.md)
- [CrackStation](crackstation.md)
- [Crunch](crunch.md)
- [Hash-Identifier](hash-identifier.md)
- [hashID](hashid.md)
- [L0phtCrack](l0phtcrack.md)
- [OnlineHashCrack](onlinehashcrack.md)
- [Ophcrack](ophcrack.md)
- [Pwdump / Pwdump7](pwdump.md)
- [RainbowCrack](rainbowcrack.md)
- [Rcalc (ambiguous source name)](rcalc.md)
- [Responder](responder.md)
- [RockYou wordlist](rockyou.md)
- [rtgen](rtgen.md)
- [SecLists](seclists.md)
- [Winrtgen](winrtgen.md)
- [WordList-Compendium](wordlist-compendium.md)

### Privilege escalation

- [getcap](getcap.md)
- [GTFOBins](gtfobins.md)
- [icacls](icacls.md)
- [id](id.md)
- [linPEAS](linpeas.md)
- [PEASS-ng](peass.md)
- [PowerSploit](powersploit.md)
- [PowerUp](powerup.md)
- [sudo](sudo.md)
- [TheFatRat](thefatrat.md)
- [Vim](vim.md)
- [whoami](whoami.md)
- [winPEAS](winpeas.md)

### Reference utilities

- [Git](git.md)
- [OWASP WSTG](owasp-wstg.md)
- [Python http.server](python-http-server.md)

### Vulnerability assessment

- [Nessus](nessus.md)

### Web testing

- [Apache HTTP Server](apache.md)
- [Browser developer tools](browser-devtools.md)
- [Burp Suite](burp-suite.md)
- [curl](curl.md)
- [Dirb](dirb.md)
- [ffuf](ffuf.md)
- [Gobuster](gobuster.md)
- [Nikto](nikto.md)
- [WPScan](wpscan.md)

### Wireless

- [iw](iw.md)

## Reading and verification limits

Priority pages cite upstream documentation where retrievable. [OpenStego](openstego.md), [Greenbone](openvas.md), [Hashes.com](hashes-com.md), [ZAP](owasp-zap.md), [SearchSploit](searchsploit.md), [VeraCrypt](veracrypt.md) and [Metasploit](metasploit.md) documentation were checked during this update. [SNOW](snow.md) upstream was inaccessible, [Steghide](steghide.md) returned an error, [HashCalc](hashcalc.md) timed out and the historical [PhoneSploit](phonesploit.md) link could not be verified. Kali package-maintainer help was checked as a fallback for [Steghide](steghide.md) and [SNOW](snow.md); unavailable vendor pages retain explicit source limitations. Other historical entries adapt existing supplied notes and do not assert current support. Tool operation is not validated by a Markdown/link check.

See [all exam domains](../README.md), [source map](../docs/imported-sources.md) and [tool directory by purpose](../docs/tool-directory.md).

## Tools added from supplied PDFs

The original 151-entry catalog now contains **161 tool/resource pages**. Ten matching existing tool files also have full PDF-text appendices. See the [complete PDF mapping](../docs/official-import.md). Original source text stays unchanged inside the imported blocks.

- [arpspoof](arpspoof.md)
- [DNSRecon](dnsrecon.md)
- [hping3](hping3.md)
- [Mimikatz](mimikatz.md)
- [Mole](mole.md)
- [OSRFramework](osrframework.md)
- [Shodan](shodan.md)
- [Snort](snort.md)
- [Svmap](svmap.md)
- [theHarvester](theharvester.md)
