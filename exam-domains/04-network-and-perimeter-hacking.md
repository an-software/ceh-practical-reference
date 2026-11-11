# 4. Network and Perimeter Hacking

Subdomains: Sniffing; Social Engineering; Denial-of-service; Session Hijacking; Evading IDS, Firewalls and Honeypots.

## Basic steps

1. Map network boundaries, permitted paths and relevant controls. Note sensor position and capture time range.
2. Inspect supplied packet captures: endpoints, conversations, protocols, DNS, HTTP requests and TCP flags. Follow relevant streams.
3. For suspected DoS, compare rates over time, source/destination distribution, incomplete handshakes and capture-loss indicators. Use supplied captures or a simulator rather than flooding a live service.
4. For session testing, compare authentication state before/after login and logout, cookie attributes, token rotation and timeout behavior using synthetic accounts.
5. For social-engineering scenarios, identify the pretext, requested action, trust cues and controls. Use approved mock artifacts and test identities; define authorization before any interaction with people.
6. Compare expected versus observed firewall/IDS behavior with narrowly scoped probes. Distinguish filtering, service failure and monitoring gaps; inspect supplied rules/logs when available.
7. Record the evidence and control improvement: encryption, segmentation, session invalidation, rate limits, detection or user reporting.

## Helpful tools

| Tool | Use |
| --- | --- |
| [Wireshark](../tools/wireshark.md), [tshark](../tools/tshark.md), [tcpdump](../tools/tcpdump.md) | Capture analysis, endpoints, streams and protocol filters |
| [Nmap](../tools/nmap.md) | Scoped reachability and firewall-behavior checks |
| [Burp Suite](../tools/burp-suite.md), [OWASP ZAP](../tools/owasp-zap.md), [browser developer tools](../tools/browser-devtools.md) | Inspect lab requests, cookies and session lifecycle |
| Firewall/IDS logs and rule viewers | Correlate traffic with configured policy and alerts |
| Email header viewer and approved awareness simulator | Analyze mock phishing artifacts and controls |
| Traffic statistics and lab replay/simulation tools | Study availability events without production disruption |

## Result check

Many SYNs alone do not establish DoS; source addresses can be spoofed. HTTPS content is not automatically readable in a capture. A TCP ACK response does not prove an open application port. Evasion is a control-validation topic, not evidence that a scan is invisible; honeypot identification is uncertain without corroboration.

Related notes: [packet forensics](../topics/forensics.md), [scan selection](../topics/reconnaissance.md), [web sessions](../topics/web-testing.md). Tool reference: [Wireshark documentation](https://www.wireshark.org/docs/).
