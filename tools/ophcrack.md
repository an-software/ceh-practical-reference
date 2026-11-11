# Ophcrack

Category: Passwords. Purpose: Rainbow-table-based Windows password recovery in historical labs.

## Basic workflow

1. Identify the supported input type.
2. Select tables for that exact hash family.
3. Verify any recovered synthetic password.

## Troubleshooting

LM/NTLM and table character/length coverage differ; incompatible tables cannot recover every password.

Related: [topic guide](../topics/passwords.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
