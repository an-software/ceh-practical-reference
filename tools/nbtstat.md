# nbtstat

Category: Enumeration. Purpose: Windows NetBIOS name and cache inspection.

## Basic workflow

1. Decide whether the input is an IP or a name.
2. Query the corresponding name table.
3. Correlate names with SMB/DNS evidence.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```powershell
nbtstat -A 192.0.2.10
```


## Troubleshooting

Uppercase -A takes an IP; lowercase -a takes a name. NetBIOS can be disabled.

Related: [topic guide](../topics/enumeration.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
