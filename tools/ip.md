# ip (iproute2)

Category: Discovery. Purpose: Inspect Linux addresses, routes and links.

## Basic workflow

1. Check local addresses.
2. Inspect the route to the lab subnet.
3. Confirm link state before troubleshooting scans.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
ip route
```


## Troubleshooting

A valid tool command cannot fix a missing VPN route or wrong VM network automatically.

Related: [topic guide](../topics/reconnaissance.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
