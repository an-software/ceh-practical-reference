# Windows net commands

Category: Enumeration. Purpose: Inspect Windows users, domain metadata and current share connections.

## Basic workflow

1. Record the current Windows/domain context.
2. Use net user or net use for the requested inventory.
3. Distinguish local from domain results.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```powershell
net user /domain
```


## Troubleshooting

Domain queries need a reachable controller and the proper context; do not copy account-creation commands for enumeration.

Related: [topic guide](../topics/enumeration.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
