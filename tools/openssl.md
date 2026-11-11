# OpenSSL

Category: Cryptography. Purpose: Digests, certificates, encoding and TLS inspection.

## Basic workflow

1. Identify the operation and input format.
2. Use a working copy and explicit options.
3. Verify the result independently.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
openssl dgst -sha256 lab-file.txt
```


## Troubleshooting

Encoding is not encryption; s_client output alone does not establish hostname/chain validation.

Related: [topic guide](../topics/cryptography.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
