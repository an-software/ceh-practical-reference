# sudo

Category: Privilege escalation. Purpose: Run explicitly permitted commands under another identity and inspect policy.

## Basic workflow

1. Record the current identity.
2. List effective permissions.
3. Review exact command/argument/environment restrictions.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
sudo -l
```


## Troubleshooting

A listed rule may contain restrictions that invalidate generic escalation examples.

Related: [topic guide](../topics/privilege-escalation.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
