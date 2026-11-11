# PhoneSploit

Priority writeup tool. Purpose: a menu wrapper around Android Debug Bridge workflows in the supplied historical notes. Different forks use the same/similar names.

## Basic workflow

1. Establish which upstream/fork/version is actually installed; review its code and dependencies.
2. Use an owned emulator or explicitly authorized device with debugging enabled and approved on the device.
3. Inspect the wrapper's current menu/help rather than copying numeric menu choices from an old writeup.
4. Confirm the device serial and identity, inspect only authorized lab data and revoke debugging access afterward.

## Example

Verify the underlying connection directly before troubleshooting the wrapper:

```bash
adb devices -l
adb -s emulator-5554 shell id
```

Tools in this example: [Android Debug Bridge (adb)](adb.md).

Use the actual authorized serial. No PhoneSploit installation or remote-device connection is performed by this repository.

## Troubleshooting

An unauthorized/offline [ADB](adb.md) device is not accessible just because its IP is known. Modern wireless debugging may require pairing. Debugging access is not inherently root. Old Python paths, misspelled commands and menu numbers are version-specific.

Related: [ADB](adb.md), [mobile workflow](../docs/lab-workflows.md). Source: supplied CEH-main Android notes; [historical linked repository](https://github.com/01010000/phonesploit) (not verified reachable during this review), [official ADB manual](https://developer.android.com/tools/adb).
