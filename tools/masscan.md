# Masscan

Category: Discovery. Purpose: Large-scale asynchronous port discovery, used cautiously in a lab.

## Basic workflow

1. Confirm the exact allowed address list.
2. Select narrow ports and a conservative packet rate.
3. Recheck candidate open ports with service-aware [Nmap](nmap.md) probes.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
masscan --help
```


## Troubleshooting

High rates can overwhelm a small lab or lose replies; discovery does not identify software versions.

Related: [topic guide](../topics/reconnaissance.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
