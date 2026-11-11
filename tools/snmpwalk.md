# snmpwalk

Category: Enumeration. Purpose: Read an authorized SNMP subtree.

## Basic workflow

1. Use the lab-supplied version and credentials.
2. Start with a narrow system-information OID.
3. Correlate exposed values with the host inventory.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
snmpwalk -v2c -c lab-community 192.0.2.10 1.3.6.1.2.1.1
```


## Troubleshooting

SNMPv3 authentication/privacy parameters must agree; do not assume every system uses a public community.

Related: [topic guide](../topics/enumeration.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
