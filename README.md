# CEH Practical Reference

## Exam outline

| Domain guide | Subdomains | Questions | Weight |
| --- | --- | ---: | ---: |
| [1. Information Security and Ethical Hacking](exam-domains/01-information-security-and-ethical-hacking.md) | Introduction to Ethical Hacking | 1 | 5% |
| [2. Reconnaissance Techniques](exam-domains/02-reconnaissance-techniques.md) | Footprinting and Reconnaissance; Scanning Networks; Enumeration | 3 | 15% |
| [3. System Hacking Phases and Attack Techniques](exam-domains/03-system-hacking-phases-and-attack-techniques.md) | Vulnerability Analysis; System Hacking; Malware Threats | 3 | 15% |
| [4. Network and Perimeter Hacking](exam-domains/04-network-and-perimeter-hacking.md) | Sniffing; Social Engineering; Denial-of-service; Session Hijacking; Evading IDS, Firewalls and Honeypots | 5 | 25% |
| [5. Web Application Hacking](exam-domains/05-web-application-hacking.md) | Hacking Web Servers; Hacking Web Applications; SQL Injection | 3 | 15% |
| [6. Tools/Systems/Programs](exam-domains/06-tools-systems-programs.md) | Hacking Wireless Networks | 1 | 5% |
| [7. Mobile Platform, IoT and OT Hacking](exam-domains/07-mobile-platform-iot-and-ot-hacking.md) | Hacking Mobile Platforms; IoT and OT Hacking | 2 | 10% |
| [8. Cloud Computing](exam-domains/08-cloud-computing.md) | Cloud Computing | 1 | 5% |
| [9. Cryptography](exam-domains/09-cryptography.md) | Cryptography | 1 | 5% |

## Topics

| Topic | Search terms |
| --- | --- |
| [Reconnaissance](topics/reconnaissance.md) | [Nmap](tools/nmap.md), DNS, discovery, ports |
| [Enumeration](topics/enumeration.md) | SMB, SNMP, shares, services |
| [Web testing](topics/web-testing.md) | HTTP, cookies, headers, directories |
| [Passwords](topics/passwords.md) | [Hashcat](tools/hashcat.md), hashes, wordlists |
| [Forensics](topics/forensics.md) | SHA256, memory, [Volatility](tools/volatility.md), packets |
| [Cryptography](topics/cryptography.md) | [OpenSSL](tools/openssl.md), Base64, certificates, TLS |
| [Wireless](topics/wireless.md) | Wi-Fi, WPA, captures, adapters |
| [Privilege escalation](topics/privilege-escalation.md) | [sudo](tools/sudo.md), SUID, permissions, Windows privileges |

## Tools

See [Tool directory](docs/tool-directory.md)

## Practical workflow

1. Record scope, targets, time limits and permitted techniques.
2. Discover services, then enumerate relevant ones.
3. Change one variable at a time and save minimal evidence.
4. Validate findings manually and record impact plus remediation.
5. Clean up lab changes; review notes for secrets before committing.
