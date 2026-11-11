# Vim

Category: Privilege escalation. Purpose: Text editor also relevant when overly broad [sudo](sudo.md) rules exist.

## Basic workflow

1. Inspect actual [sudo](sudo.md) policy.
2. Read the allowed program/context carefully.
3. Document why unnecessary privileged editor access is risky.

## Troubleshooting

An installed editor alone is not escalation; do not overwrite system files to prove mere presence.

Related: [topic guide](../topics/privilege-escalation.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
