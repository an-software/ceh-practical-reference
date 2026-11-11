# tshark

Category: Forensics. Purpose: Command-line packet decoding/statistics from Wireshark.

## Basic workflow

1. Open a working-copy capture.
2. Use display filters and selected output fields.
3. Correlate timestamps/endpoints before interpreting results.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
tshark -r lab.pcapng -q -z conv,tcp
```


## Troubleshooting

Display filters and capture filters use different syntax; encryption and packet loss limit visibility.

Related: [topic guide](../topics/forensics.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
