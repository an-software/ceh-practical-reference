# linPEAS

Category: Privilege escalation. Purpose: Linux local privilege-enumeration member of PEASS.

## Basic workflow

1. Record current identity and kernel/distribution.
2. Review and run only within lab authorization.
3. Validate suspicious [sudo](sudo.md)/SUID/capability/path findings.

## Troubleshooting

Kernel version alone may miss backported fixes; enumeration output can contain secrets.

Related: [topic guide](../topics/privilege-escalation.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
