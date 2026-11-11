# Netdiscover

Category: Discovery. Purpose: ARP-based discovery on a local Ethernet segment.

## Basic workflow

1. Confirm the local interface and subnet.
2. Choose a narrow authorized range.
3. Correlate discovered IP/MAC pairs with the lab inventory.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
netdiscover -h
```


## Troubleshooting

ARP does not enumerate arbitrary routed networks; the selected adapter and VM network mode matter.

Related: [topic guide](../topics/reconnaissance.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
