# CeWL

Category: Passwords. Purpose: Generate a wordlist from authorized lab website text.

## Basic workflow

1. Choose an in-scope URL and shallow crawl depth.
2. Set minimum length and output path.
3. Review/deduplicate the resulting candidates.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
cewl -d 1 -m 5 -w evidence/lab-words.txt http://192.0.2.10/
```


## Troubleshooting

Site text is not proof of a password; do not crawl unrelated external sites.

Related: [topic guide](../topics/passwords.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
