# getcap

Category: Privilege escalation. Purpose: Inspect Linux file capabilities.

## Basic workflow

1. Read capabilities on scoped executable paths.
2. Identify unusual privileges.
3. Correlate with actual user-accessible binary behavior.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
getcap -r /usr/bin /usr/sbin
```


## Troubleshooting

No output can mean none found or insufficient visibility; capability presence still needs context.

Related: [topic guide](../topics/privilege-escalation.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
