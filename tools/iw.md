# iw

Category: Wireless. Purpose: Inspect Linux wireless interfaces and hardware capabilities.

## Basic workflow

1. List interfaces.
2. Review supported modes and channels.
3. Relate the adapter to the lab AP/capture.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
iw dev
```


## Troubleshooting

Driver/VM passthrough limitations can prevent monitor mode; do not assume interface names.

Related: [topic guide](../topics/wireless.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
