# 2. Reconnaissance Techniques

Subdomains: Footprinting and Reconnaissance; Scanning Networks; Enumeration.

## Basic steps

1. Confirm the target subnet, VPN route and DNS configuration. Gather supplied/public host and domain information.
2. Discover authorized hosts; choose ARP for the local segment or suitable IP probes for routed targets.
3. Scan relevant TCP ports, then broaden if required. Test UDP separately when the task calls for it.
4. Identify service versions and likely operating systems; corroborate fingerprints rather than relying on a port number.
5. Enumerate relevant services: DNS records, SMB shares/domain information, SNMP metadata, web virtual hosts and database banners.
6. Build a host table with IP, hostname, ports, service/version, identity used, evidence location and next hypothesis.

## Helpful tools

| Tool | Use |
| --- | --- |
| [Nmap](../tools/nmap.md) | Discovery, TCP/UDP scans, service and OS fingerprinting; review NSE scripts before use |
| [`ip route`](../tools/ip.md), [`getent`](../tools/getent.md), [`dig`](../tools/dig.md), [`nslookup`](../tools/nslookup.md) | Routing and name-resolution checks |
| [Netdiscover](../tools/netdiscover.md) | Local-segment discovery |
| [smbclient](../tools/smbclient.md), [enum4linux](../tools/enum4linux.md), [rpcclient](../tools/rpcclient.md) | SMB/share/domain enumeration |
| [snmpwalk](../tools/snmpwalk.md), [snmp-check](../tools/snmp-check.md) | Authorized SNMP metadata collection |
| [curl](../tools/curl.md), browser, [Wireshark](../tools/wireshark.md) | Confirm application behavior and investigate reachability |

## Result check

Distinguish filtered from closed ports and failed authentication from failed connectivity. A silent ping does not prove a host is down. Keep broad scans and rate settings appropriate to the lab.

Related notes: [reconnaissance](../topics/reconnaissance.md), [enumeration and common ports](../topics/enumeration.md).
