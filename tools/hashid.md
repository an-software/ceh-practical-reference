# hashID

Category: Passwords. Purpose: Suggest hash formats from textual appearance.

## Basic workflow

1. Use a synthetic or authorized sample.
2. Compare candidate formats with the source application.
3. Verify against the recovery tool's example input.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
hashid -h
```


## Troubleshooting

Length/prefix heuristics do not identify every algorithm or salt layout with certainty.

Related: [topic guide](../topics/passwords.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
