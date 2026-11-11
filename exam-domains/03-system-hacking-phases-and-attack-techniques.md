# 3. System Hacking Phases and Attack Techniques

Subdomains: Vulnerability Analysis; System Hacking; Malware Threats.

## Basic steps

1. Use the service inventory to identify candidate weaknesses; compare exact product, version, configuration and patch status.
2. Review scanner findings and exploit references for prerequisites. Validate one hypothesis with minimal lab impact.
3. For password tasks, identify the actual hash format and use a small lab wordlist before expanding recovery attempts.
4. After authorized access, record the current user, groups, OS and privileges. Enumerate [sudo](../tools/sudo.md) rules, SUID/capabilities, service permissions and scheduled tasks.
5. Validate a specific privilege/configuration finding and record its remediation; a tool highlight alone is insufficient.
6. For suspicious files, preserve a copy, hash it, inspect format/headers, strings and entry point, then correlate host/network evidence. Use isolated environments for any dynamic analysis.
7. Record access level achieved, limitations and cleanup. Preserve logs rather than treating log clearing as routine cleanup.

## Helpful tools

| Tool | Use |
| --- | --- |
| [Nmap](../tools/nmap.md), [OpenVAS/Greenbone](../tools/openvas.md), [SearchSploit](../tools/searchsploit.md) | Candidate discovery, scanner evidence/CVE references and exploit-reference matching |
| [John Jumbo](../tools/john.md), [Hashcat](../tools/hashcat.md) | Offline recovery of supplied lab hashes |
| [`id`](../tools/id.md), [`sudo -l`](../tools/sudo.md), [`getcap`](../tools/getcap.md), [`whoami`](../tools/whoami.md), [`icacls`](../tools/icacls.md) | Verify identity and permissions |
| [PEASS](../tools/peass.md), reviewed [PowerUp](../tools/powerup.md) checks, [GTFOBins](../tools/gtfobins.md) | Enumeration leads and behavior references |
| [Metasploit](../tools/metasploit.md) | Explicitly scoped exploit/session validation in disposable labs |
| [strings](../tools/strings.md), [readelf](../tools/readelf.md)/[objdump](../tools/objdump.md), [Ghidra](../tools/ghidra.md), [radare2](../tools/radare2.md), [YARA](../tools/yara.md) | Static file and executable analysis |
| [Volatility](../tools/volatility.md), [ProcMon](../tools/procmon.md), [Wireshark](../tools/wireshark.md) | Correlate memory, process and network evidence |

## Result check

A kernel version may include backported fixes. A reverse shell does not imply administrator access. High entropy or suspicious strings do not prove malware. Never execute unknown samples on the normal workstation.

Related notes: [passwords](../topics/passwords.md), [privilege escalation](../topics/privilege-escalation.md), [forensics](../topics/forensics.md), [lab workflows](../docs/lab-workflows.md).
