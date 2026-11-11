# ffuf

Category: Web testing. Purpose: Place a wordlist into a selected request position.

## Basic workflow

1. Capture the correct request/host context.
2. Mark one FUZZ position and set a conservative rate.
3. Review results against baseline responses.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
ffuf -u http://192.0.2.10/FUZZ -w paths.txt -rate 10 -mc all
```


## Troubleshooting

Filters can hide real responses if chosen before measuring wildcard behavior.

Related: [topic guide](../topics/web-testing.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
