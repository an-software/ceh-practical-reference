# snmp-check

Category: Enumeration. Purpose: Summarize exposed SNMP information.

## Basic workflow

1. Read local options for version/community settings.
2. Query only the authorized lab host.
3. Review interfaces/process details as permitted.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
snmp-check -h
```


## Troubleshooting

This is SNMP enumeration, not NetBIOS user enumeration.

Related: [topic guide](../topics/enumeration.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
