# rpcclient

Category: Enumeration. Purpose: Samba client for RPC metadata queries.

## Basic workflow

1. Confirm server reachability and identity.
2. Query limited domain/user metadata.
3. Save the relevant response and visibility limits.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
rpcclient -U labuser 192.0.2.10 -c 'querydominfo'
```


## Troubleshooting

Anonymous RPC is often denied; that does not imply an absent domain.

Related: [topic guide](../topics/enumeration.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
