# readelf

Category: Forensics. Purpose: Inspect ELF executable headers and metadata.

## Basic workflow

1. Use a copied ELF file.
2. Read architecture and entry-point information.
3. Relate virtual addresses to sections/segments.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
readelf -h lab-sample.elf
```


## Troubleshooting

An ELF entry address is not necessarily a file offset.

Related: [topic guide](../topics/forensics.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
