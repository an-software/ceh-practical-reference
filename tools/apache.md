# Apache HTTP Server

Category: Web testing. Purpose: Web server used in historical lab transfer/deployment examples.

## Basic workflow

1. Identify the configured document root and bind address.
2. Use a dedicated lab site with minimum files.
3. Review access logs and restore test configuration.

## Troubleshooting

Starting a system service changes exposure; old /var/www/html assumptions may not match the installed setup.

Related: [topic guide](../topics/web-testing.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
