# Nikto

Category: Web testing. Purpose: Web-server configuration and known-file assessment.

## Basic workflow

1. Confirm host/port and scope.
2. Run a focused lab scan.
3. Manually verify each relevant finding.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
nikto -h http://192.0.2.10/
```


## Troubleshooting

An informational disclosure or version match alone is not a confirmed vulnerability.

Related: [topic guide](../topics/web-testing.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
