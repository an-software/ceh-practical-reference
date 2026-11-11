# Metasploit Framework

Priority writeup tool. Purpose: modular lab validation, service checks and management of explicitly authorized test sessions.

## Basic workflow

1. Match the exact product/version and module prerequisites to the lab target.
2. Read the module information and options, including authentication and side effects.
3. Prefer a focused scanner/check where appropriate; validate impact and record actual session identity.

## Example

Module inspection only; these console commands do not launch an exploit:

```text
msfconsole
search type:auxiliary name:smb_version
use auxiliary/scanner/smb/smb_version
info
show options
back
```

## Troubleshooting

Module availability varies by version. A session is not automatically elevated. Payload/handler, architecture and reachable callback address must agree. `check` is not universally available or harmless; read module behavior first. Remove documented lab artifacts and preserve logs.

Related: [system-hacking domain](../exam-domains/03-system-hacking-phases-and-attack-techniques.md). Source: [Metasploit documentation](https://docs.metasploit.com/).
