# 7. Mobile Platform, IoT and OT Hacking

Subdomains: Hacking Mobile Platforms; IoT and OT Hacking.

## Basic steps

1. Inventory the lab device, firmware/OS, interfaces, application and network dependencies. Distinguish a mobile app, IoT endpoint and industrial control component.
2. Use an owned emulator or explicitly authorized device. Verify debugging authorization and record device identity before inspection.
3. Review mobile permissions, exported components, local data handling and API authentication using synthetic app data.
4. For IoT, inspect documented services, management interfaces, configuration and supplied firmware/captures. Check whether authentication and encrypted transport protect messages.
5. Identify relevant protocols from evidence: HTTP, MQTT/CoAP or industrial traffic such as Modbus. Correlate endpoints and operations with the lab diagram.
6. For OT, start with passive capture and configuration review. Use a simulator for active validation; avoid writes, resets or broad scans against physical controllers without a specific approved procedure.
7. Record the weakness and impact on confidentiality, integrity, availability and physical operation; restore test settings and revoke debugging access.

## Helpful tools

| Tool | Use |
| --- | --- |
| [Android Studio emulator](../tools/android-studio.md) and [Android SDK adb](../tools/adb.md) | Authorized device identity, shell access and debugging |
| [JADX](../tools/jadx.md), [APKTool](../tools/apktool.md) | Static inspection of a lab Android package and manifest |
| [Burp Suite](../tools/burp-suite.md), [OWASP ZAP](../tools/owasp-zap.md) | Inspect authorized app/API traffic when the test setup permits it |
| [Wireshark](../tools/wireshark.md), [tshark](../tools/tshark.md) | MQTT, CoAP, industrial protocol and endpoint analysis |
| [file](../tools/file.md), [strings](../tools/strings.md), [binwalk](../tools/binwalk.md), [Ghidra](../tools/ghidra.md) | Identify and inspect supplied firmware or executable copies |
| Vendor documentation and OT simulator | Interpret protocol functions and validate without altering live equipment |
| [Nmap](../tools/nmap.md) | Narrow discovery only where device-specific scope permits active probes |

## Result check

An [ADB](../tools/adb.md) connection requires device authorization; it does not inherently grant root or access to protected app storage. A firmware string may be unused. An open industrial port is not permission to issue control commands. Encryption may limit application-payload visibility.

Related notes: [Android lab workflow](../docs/lab-workflows.md), [static and packet forensics](../topics/forensics.md), [official ADB documentation](https://developer.android.com/tools/adb).
