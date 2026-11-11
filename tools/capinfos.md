# capinfos

Category: Forensics. Purpose: Summarize capture file metadata.

## Basic workflow

1. Inspect format, packet count and duration.
2. Check timestamps and capture characteristics.
3. Use [Wireshark](wireshark.md)/[tshark](tshark.md) for detailed interpretation.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
capinfos lab.pcapng
```


## Troubleshooting

Metadata alone does not establish capture completeness or an attack.

Related: [topic guide](../topics/forensics.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
