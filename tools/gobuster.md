# Gobuster

Category: Web testing. Purpose: Dictionary-based discovery of web paths or other supported targets.

## Basic workflow

1. Choose the correct mode and scoped URL.
2. Use a small lab list and limited concurrency.
3. Compare responses against a random nonexistent path.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
gobuster dir -u http://192.0.2.10/ -w paths.txt -t 5
```


## Troubleshooting

Wildcard routes and custom error pages can create false positives.

Related: [topic guide](../topics/web-testing.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
