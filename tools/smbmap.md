# smbmap

Category: Enumeration. Purpose: Inspect SMB share permissions for a lab identity.

## Basic workflow

1. Check the installed version and connection options.
2. Enumerate authorized shares and effective permissions.
3. Verify the specific file/path manually.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
smbmap --help
```


## Troubleshooting

Remote-execution options are separate from share enumeration and need separate scope.

Related: [topic guide](../topics/enumeration.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
