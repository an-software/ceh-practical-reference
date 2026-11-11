# icacls

Category: Privilege escalation. Purpose: Inspect Windows file/directory ACLs.

## Basic workflow

1. Inspect the exact executable/data path.
2. Identify applicable user/group permissions.
3. Correlate with service identity and parent-path behavior.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```powershell
icacls C:\ProgramData
```


## Troubleshooting

A writable parent directory alone is not always a complete exploitation path.

Related: [topic guide](../topics/privilege-escalation.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
