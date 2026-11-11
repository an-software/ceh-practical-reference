# Python http.server

Category: Reference utilities. Purpose: Serve a deliberately selected directory in an isolated transfer lab.

## Basic workflow

1. Create a directory containing only synthetic transfer files.
2. Bind the intended local interface/port.
3. Stop the server when done.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
python3 -m http.server --help
```


## Troubleshooting

Serving the repository root can disclose unrelated files; Python 2 SimpleHTTPServer syntax is obsolete.

Related: [lab workflows](../docs/lab-workflows.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
