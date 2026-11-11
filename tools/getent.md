# getent

Category: Discovery. Purpose: Query Unix name-service databases through configured lookup sources.

## Basic workflow

1. Identify the desired host entry.
2. Query via the configured name-service stack.
3. Compare with raw DNS when troubleshooting.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
getent hosts lab.example
```


## Troubleshooting

Results may include local hosts-file or other configured sources, not just DNS.

Related: [topic guide](../topics/reconnaissance.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
