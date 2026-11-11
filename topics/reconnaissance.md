# Reconnaissance

Keywords: [Nmap](../tools/nmap.md) DNS discovery TCP ports scope.

Discover hosts, identify relevant ports, then inspect services. These are reserved documentation IPs: replace them with your authorized lab addresses.

```bash
mkdir -p evidence
ip route
getent hosts lab.example
nmap -sn 192.0.2.0/24 -oA evidence/discovery
nmap -sT -sV --open -p 22,80,443,445 192.0.2.10 -oA evidence/services
dig lab.example A
dig lab.example MX
```

Tools in this example: [dig](../tools/dig.md), [getent](../tools/getent.md), [ip (iproute2)](../tools/ip.md), [Nmap](../tools/nmap.md).

Record hostname, address, port, protocol, version and confidence. TCP connect scans (`-sT`) work without raw-socket privileges. Use `-Pn` only for a known host when discovery is filtered; it scans even if discovery probes get no answer.

Troubleshooting: verify VPN routes and scope. A silent ping does not prove a host is down. Filtered ports may indicate a firewall. UDP needs separate testing and may be slow. A version banner alone does not prove vulnerability.

Sources: [Nmap](https://github.com/nmap/nmap), [official reference](https://nmap.org/book/man.html).

## Discovery and scan selection from supplied notes

```bash
# ARP discovery is useful on the local Ethernet segment:
sudo nmap -sn -PR 192.0.2.0/24
sudo nmap -sn -PE -PS22,80,443 -PA80 192.0.2.10
sudo nmap -sn -PU53,161 192.0.2.10
# Broad TCP inventory, followed by a focused version check:
nmap -sT -p- --open 192.0.2.10 -oA evidence/all-tcp
nmap -sT -sV -p 21,22,80,443,1433,3306,3389 192.0.2.10
sudo nmap -sU -sV -p 53,161 192.0.2.10 -oA evidence/udp
sudo nmap -O --osscan-limit 192.0.2.10
nmap -6 -sT -p 80,443 2001:db8::10
sudo nmap -sV --script smb-os-discovery -p 445 192.0.2.10
```

Tools in this example: [Nmap](../tools/nmap.md).

Use an explicitly scoped subnet only. `-p-` covers all ports of the selected transport; it does not implicitly enable UDP. IPv6 needs an IPv6 route. OS detection benefits from an open and closed TCP port and remains a fingerprint estimate.

| Technique | Meaning and limitation |
| --- | --- |
| `-sS` | SYN scan; usually requires elevated privileges; still detectable |
| `-sT` | Full TCP connect scan; suitable without raw-socket access |
| `-sU` | UDP scan; silence often produces open-or-filtered ambiguity |
| `-sA` | ACK firewall mapping; does not establish that a port is open |
| `-sN`, `-sF`, `-sX`, `-sM` | NULL/FIN/Xmas/Maimon; behavior depends on TCP stack/firewall |
| `-sI ZOMBIE TARGET` | Idle scan requires a suitable authorized intermediary; source shorthand omitted that mandatory argument |
| `-sY`, `-sZ` | SCTP INIT/COOKIE-ECHO scans for SCTP services |
| `-PP`, `-PM`, `-PO` | Timestamp/address-mask/IP-protocol discovery probes; often filtered |
| `-A` | Enables OS/version detection, default scripts and traceroute; broader than OS detection alone |
| `-sC` | Default NSE scripts; review script behavior before running |

Save normal/XML output with `-oA`; create the parent directory first. Prefer normal timing initially; high minimum rates or `-T5` may miss services on a slow lab/VPN. Fragmentation and spoofing options from older notes are special cases, not a reliable invisibility technique.
