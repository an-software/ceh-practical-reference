# whoami

Category: Privilege escalation. Purpose: Report current identity and, on Windows, token/group details.

## Basic workflow

1. Run in the relevant session.
2. Capture current identity/token context.
3. Compare to the permissions needed for the task.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```powershell
whoami /all
```


## Troubleshooting

Windows and Unix options differ; account names alone do not show all effective restrictions.

Related: [topic guide](../topics/privilege-escalation.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
