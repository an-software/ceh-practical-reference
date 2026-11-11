# sha256sum

Category: Cryptography. Purpose: Calculate SHA256 file digests on Linux.

## Basic workflow

1. Hash the intended file bytes.
2. Record filename and digest.
3. Compare copies/reference values with the same algorithm.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
sha256sum lab-file.txt
```


## Troubleshooting

Line-ending/encoding changes alter the digest; a digest alone does not identify an author.

Related: [topic guide](../topics/cryptography.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
