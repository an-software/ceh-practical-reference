# strings

Category: Forensics. Purpose: Find printable character sequences in a binary.

## Basic workflow

1. Analyze a copy.
2. Choose a useful minimum length/encoding.
3. Correlate strings with header/code/network evidence.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
strings -a -n 8 lab-sample.bin
```


## Troubleshooting

Strings can be unused or planted; they do not prove execution.

Related: [topic guide](../topics/forensics.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
