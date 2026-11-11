# MySQL client

Category: Enumeration. Purpose: Authenticated database inspection in an authorized lab.

## Basic workflow

1. Connect with the correct host/user and password prompt.
2. List only permitted schemas/tables.
3. Read the minimum required synthetic data.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
mysql -h 192.0.2.10 -u labuser -p
```


## Troubleshooting

Lowercase -p prompts for a password; uppercase -P selects a port.

Related: [topic guide](../topics/enumeration.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
