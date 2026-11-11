# 6. Tools/Systems/Programs

Subdomain: Hacking Wireless Networks. The broad domain title is retained from the supplied outline; this guide focuses on its stated wireless subdomain.

## Basic steps

1. Identify the authorized access point and client, SSID/BSSID, channel and authentication type.
2. Check adapter/driver capabilities and the environment: managed versus monitor mode, VM passthrough and capture support.
3. Inspect a supplied capture for management and authentication traffic. Confirm that it belongs to the intended lab network.
4. For a compatible WPA/WPA2-Personal exercise, confirm suitable authentication material and try the supplied small wordlist offline.
5. Compare any recovered lab key with the expected network identity. Record protocol limitations rather than assuming the same workflow covers WPA3 or enterprise authentication.
6. Restore normal adapter/network settings and keep captures and recovered keys outside Git.

## Helpful tools

| Tool | Use |
| --- | --- |
| [`iw`](../tools/iw.md), [`ip link`](../tools/ip.md) | Interfaces, channel/capability information and link state |
| [Wireshark](../tools/wireshark.md), [capinfos](../tools/capinfos.md) | Capture metadata, Wi-Fi frames and EAPOL inspection |
| [Aircrack-ng suite](../tools/aircrack-ng.md) | Compatible wireless capture analysis and offline lab recovery |
| [Hashcat](../tools/hashcat.md) | Supported offline wireless recovery formats after verifying input requirements |

## Result check

A similar SSID does not establish a rogue AP. Missing authentication material, weak signal, an incorrect BSSID or incompatible capture format can prevent recovery. WSL may not expose the necessary adapter capabilities. These basic steps do not require disruptive deauthentication.

Related notes: [wireless commands](../topics/wireless.md), [password recovery](../topics/passwords.md), [Aircrack-ng manual](https://www.aircrack-ng.org/doku.php?id=main).
