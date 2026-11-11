# netstat

Category: Enumeration. Purpose: Inspect local network connections/listeners.

## Basic workflow

1. Run on the host whose connections matter.
2. Identify listeners and remote endpoints.
3. Correlate with process details using the available OS options.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```powershell
netstat -an
```


## Troubleshooting

Passing a remote IP does not make netstat enumerate that remote host's users.

Related: [topic guide](../topics/enumeration.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
