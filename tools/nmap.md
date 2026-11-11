# Nmap

Priority writeup tool. Purpose: host discovery, port/service inventory and OS fingerprinting.

## Basic workflow

1. Verify scope, interface and route; discover hosts before broad scanning.
2. Scan TCP ports, then run focused version detection. Select UDP separately.
3. Corroborate version/OS estimates and save normal/XML evidence.

## Example

Linux lab; replace reserved documentation addresses:

```bash
mkdir -p evidence
nmap -sn 192.0.2.0/24 -oA evidence/discovery
nmap -sT -sV -p 21,22,80,443,445,3389 192.0.2.10 -oA evidence/services
sudo nmap -sU -sV -p 53,161 192.0.2.10
```

## Troubleshooting

Filtered is not closed. A silent ping does not prove a host is absent. `-p-` alone does not scan UDP. SYN scans still produce detectable traffic; review NSE script behavior before selecting scripts.

Related: [reconnaissance](../topics/reconnaissance.md), [enumeration](../topics/enumeration.md). Source: [Nmap manual](https://nmap.org/book/man.html).

