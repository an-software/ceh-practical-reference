# Dirb

Category: Web testing. Purpose: Dictionary-based web content discovery.

## Basic workflow

1. Confirm the application base path.
2. Select a small relevant wordlist.
3. Validate candidate paths in the browser/proxy.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
dirb http://192.0.2.10/ paths.txt
```


## Troubleshooting

A 403 or unusual length alone is not proof of sensitive content.

Related: [topic guide](../topics/web-testing.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
