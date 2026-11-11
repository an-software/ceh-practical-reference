# enum4linux

Category: Enumeration. Purpose: SMB-related host, share and domain enumeration.

## Basic workflow

1. Confirm SMB reachability.
2. Use lab credentials or explicitly permitted anonymous access.
3. Record actual readable information and access denials.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
enum4linux -a 192.0.2.10
```


## Troubleshooting

Legacy enum4linux and enum4linux-ng are distinct implementations; permissions and SMB settings affect output.

Related: [topic guide](../topics/enumeration.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
