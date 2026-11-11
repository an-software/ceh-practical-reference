# hexdump

Category: Forensics. Purpose: Inspect raw file bytes and signatures.

## Basic workflow

1. Work from a copy.
2. Compare header/offset bytes with expected format.
3. Correlate embedded data with parser results.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
hexdump -C lab-file.bin
```


## Troubleshooting

Readable fragments do not establish a complete hidden payload or correct file type.

Related: [topic guide](../topics/forensics.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
