# dig

Category: Discovery. Purpose: Inspect DNS answers and record types.

## Basic workflow

1. Use the intended resolver/domain.
2. Request the relevant record type.
3. Record answers and TTL/context.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
dig lab.example A
```


## Troubleshooting

Missing records may reflect resolver choice, caching or scope rather than a missing host.

Related: [topic guide](../topics/reconnaissance.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
