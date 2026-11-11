# Dependency Walker

Category: Forensics. Purpose: Historical Windows executable import/dependency viewer.

## Basic workflow

1. Use a copied executable and matching architecture.
2. Inspect imported modules/functions.
3. Corroborate apparent missing dependencies on the actual OS.

## Troubleshooting

Modern Windows API-set behavior can look like missing DLLs in older tools.

Related: [topic guide](../topics/forensics.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
