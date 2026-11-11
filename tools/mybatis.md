# MyBatis

Category: Historical SQL tools. Purpose: Persistence framework, not a generic SQL injection scanner.

## Basic workflow

1. Inspect the lab application's query mappings.
2. Look for unsafe dynamic string construction.
3. Confirm parameter binding and test a minimal case.

## Troubleshooting

Using a framework does not automatically prevent SQLi; do not install it as a scanning tool.

Related: [topic guide](../topics/web-testing.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
