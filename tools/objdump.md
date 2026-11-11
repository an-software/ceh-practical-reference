# objdump

Category: Forensics. Purpose: Inspect supported binary headers and disassembly.

## Basic workflow

1. Confirm format/architecture support.
2. Read file/entry metadata.
3. Correlate with a second parser.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
objdump -f lab-sample.exe
```


## Troubleshooting

A mismatched tool build may not support every PE/ELF architecture.

Related: [topic guide](../topics/forensics.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
