# Android Debug Bridge (adb)

Category: Mobile and cloud. Purpose: Communicate with an authorized Android emulator/debugging device.

## Basic workflow

1. List approved devices.
2. Select the exact serial.
3. Inspect identity or a permitted lab property and revoke access afterward.

## Example

Run manually in the appropriate authorized lab environment; replace sample names/addresses and check installed-version help.

```bash
adb devices -l
```


## Troubleshooting

Unauthorized/offline devices need approval or connectivity fixes; debugging is not inherently root.

Related: [mobile/cloud domain index](../README.md), [tool index](README.md). Sources: the [existing tool directory](../docs/tool-directory.md), [supplied source map](../docs/imported-sources.md), and corresponding linked topic/domain notes. Historical entries document the supplied name without asserting current availability; review the installed tool's own help before use.
