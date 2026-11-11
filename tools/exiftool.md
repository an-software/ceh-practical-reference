# ExifTool

Category: Forensics. Purpose: Inspect file metadata and actual format information.

## Basic workflow

1. Work on an evidence copy.
2. Read relevant metadata.
3. Correlate timestamps/author fields with other evidence.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
exiftool lab-image.jpg
```


## Troubleshooting

Metadata can be absent or edited; do not treat it as definitive attribution.

Related: [topic guide](../topics/forensics.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
