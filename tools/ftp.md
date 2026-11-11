# FTP client

Category: Enumeration. Purpose: Interactive retrieval of an authorized lab file.

## Basic workflow

1. Connect and log in using the supplied account.
2. Inspect pwd/ls and choose binary mode if needed.
3. Retrieve only the requested file and hash it.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
ftp 192.0.2.10
```


## Troubleshooting

Control login and data-channel transfer have different failure modes; plaintext FTP is not SFTP.

Related: [topic guide](../topics/enumeration.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
