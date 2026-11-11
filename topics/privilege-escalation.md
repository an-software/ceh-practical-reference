# Privilege escalation

Keywords: Linux [sudo](../tools/sudo.md) SUID capabilities Windows privileges permissions PEASS.

Begin with read-only local enumeration after authorized access. Identify specific configuration weaknesses, validate lab impact and record least-privilege remediation.

Linux:

```bash
id
uname -a
sudo -l
find /usr/bin /usr/sbin -type f -perm -4000 2>/dev/null
getcap -r /usr/bin /usr/sbin 2>/dev/null
ls -ld /etc/cron* /etc/systemd/system
```

Tools in this example: [getcap](../tools/getcap.md), [id](../tools/id.md), [sudo](../tools/sudo.md).

Windows PowerShell / built-in command tools:

```powershell
whoami /all
Get-CimInstance Win32_Service | Select-Object Name,StartName,PathName
icacls C:\ProgramData
Get-ScheduledTask | Select-Object TaskName,TaskPath,State
```

Tools in this example: [icacls](../tools/icacls.md), [whoami](../tools/whoami.md).

Prioritize unexpected writable service paths, excessive [sudo](../tools/sudo.md) permissions, unusual capabilities and overprivileged tasks. Suspicious settings need manual validation. Review [PEASS](../tools/peass.md) source before execution and verify its findings rather than treating highlights as proof.

Troubleshooting: permission denied/access denied is expected in many locations; document visibility limits. Restricted tokens limit enumeration. Kernel versions alone do not prove vulnerability because distributions backport patches. Prefer demonstrating configuration impact over destabilizing a lab with kernel exploits.

Sources: [PEASS-ng](https://github.com/peass-ng/PEASS-ng), [HackTricks](https://github.com/HackTricks-wiki/hacktricks).

## From discovery to a validated finding

The supplied notes mention an editor allowed by [sudo](../tools/sudo.md), writable service/DLL paths and PowerUp. First capture [`sudo -l`](../tools/sudo.md) or the relevant Windows ACL and service identity. Compare the exact binary, arguments, environment restrictions and writable path with its documented behavior. [GTFOBins](https://gtfobins.github.io/) catalogs Unix program behaviors; presence of a listed binary is not proof that the current user can escalate.

For Windows, check whether the unprivileged identity can alter the exact executable or DLL search location used by a privileged service; writable parent folders alone may not be sufficient. [PowerUp](../tools/powerup.md)/[PowerSploit](../tools/powersploit.md) and [PEASS](../tools/peass.md) can provide leads, but review their code and validate output manually. Do not bypass machine-wide execution policy or create administrator accounts just to confirm an enumeration result.

[Metasploit](../tools/metasploit.md) sessions, reverse shells and RATs in the source notes are access mechanisms; they do not inherently grant higher privilege. Record identity before and after an explicitly authorized lab validation, the affected permission, and remediation. Preserve logs and remove only your documented lab artifacts afterward. The imports' log-clearing and persistence examples are retained as historical source context, not routine cleanup instructions.

See [cross-topic workflows](../docs/lab-workflows.md) for Android/[ADB](../tools/adb.md), exploit-reference triage and session troubleshooting.
