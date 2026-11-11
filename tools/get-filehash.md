# Get-FileHash

Category: Cryptography. Purpose: PowerShell file-integrity digest calculation.

## Basic workflow

1. Choose an explicit algorithm and literal path.
2. Hash originals/copies as needed.
3. Record or compare resulting values.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath .\lab-file.txt
```


## Troubleshooting

This hashes file bytes, not a password string; paths/encodings matter.

Related: [topic guide](../topics/cryptography.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
