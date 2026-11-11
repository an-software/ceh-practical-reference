# curl

Category: Web testing. Purpose: Inspect HTTP requests, responses and TLS behavior.

## Basic workflow

1. Confirm URL/virtual host.
2. Save headers/body separately.
3. Compare redirects and authenticated state.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
curl -I http://192.0.2.10/
```


## Troubleshooting

Older PowerShell aliases curl; use curl.exe there. Avoid disabling certificate checks to mask hostname/CA issues.

Related: [topic guide](../topics/web-testing.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
