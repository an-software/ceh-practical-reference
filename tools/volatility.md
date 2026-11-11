# Volatility 3

Category: Forensics. Purpose: Memory-image process/network/artifact analysis.

## Basic workflow

1. Confirm image OS and integrity.
2. Select appropriate plugins and obtain required symbols.
3. Correlate processes and network results.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
python3 vol.py -f memory.raw windows.info
```


## Troubleshooting

Volatility 2 and 3 differ; missing symbols or truncated images may prevent analysis.

Related: [topic guide](../topics/forensics.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
