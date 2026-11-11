# smbclient

Category: Enumeration. Purpose: List and access SMB shares with an authorized identity.

## Basic workflow

1. List shares with the correct account/domain.
2. Connect only to an in-scope share.
3. Retrieve the lab-required file and record access level.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
smbclient -L //192.0.2.10 -U labuser
```


## Troubleshooting

Listing a share is not proof it is readable or writable; prefer password prompts to command-line secrets.

Related: [topic guide](../topics/enumeration.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
