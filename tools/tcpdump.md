# tcpdump

Category: Forensics. Purpose: Capture or inspect packets with a compact command-line tool.

## Basic workflow

1. Select an authorized interface or existing capture.
2. Use a narrow filter.
3. Preserve the capture and note collection conditions.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
tcpdump -nn -r lab.pcap
```


## Troubleshooting

Capture filters do not use [Wireshark](wireshark.md) display-filter syntax; privileges may be required for live capture.

Related: [topic guide](../topics/forensics.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
