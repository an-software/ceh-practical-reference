# WPScan

Category: Web testing. Purpose: WordPress component/user enumeration and security references.

## Basic workflow

1. Confirm the WordPress base directory and port.
2. Enumerate only needed metadata.
3. Corroborate components and vulnerability prerequisites.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
wpscan --url http://192.0.2.10:8080/CEH/ --enumerate u
```


## Troubleshooting

Vulnerability metadata may need a token; store it outside Git. Old -u/-P examples may not match current options.

Related: [topic guide](../topics/web-testing.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
