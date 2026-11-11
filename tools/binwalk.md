# binwalk

Category: Forensics. Purpose: Inspect firmware/files for embedded signatures and related structure.

## Basic workflow

1. Hash a working copy.
2. Run identification before extraction.
3. Review offsets and extracted objects in isolation.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
binwalk lab-firmware.bin
```


## Troubleshooting

Version-dependent extraction options and external helpers can execute complex parsers; a signature hit alone is not proof.

Related: [topic guide](../topics/forensics.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
