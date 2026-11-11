# zsteg

Category: Forensics. Purpose: Analyze bit-plane hidden data in supported PNG/BMP images.

## Basic workflow

1. Identify the real image format.
2. Inspect candidate embedded-data reports.
3. Validate any extracted payload independently.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
zsteg lab-image.png
```


## Troubleshooting

This is not the general-purpose equivalent of [Steghide](steghide.md) for JPEG covers.

Related: [topic guide](../topics/forensics.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
