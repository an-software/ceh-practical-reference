# Aircrack-ng

Priority writeup tool suite. Purpose: wireless capture analysis and supported offline Wi-Fi lab key recovery.

## Basic workflow

1. Identify the lab AP's SSID/BSSID and authentication type.
2. Inspect the supplied capture for suitable authentication material.
3. Use the lab wordlist offline and verify any result against the intended AP.

## Example

Replace the example BSSID with the lab AP:

```bash
aircrack-ng -w lab-words.txt -b 02:00:00:00:00:01 lab-wifi.cap
```

## Troubleshooting

This example targets compatible WPA/WPA2-Personal material, not every wireless protocol. Missing handshakes, wrong BSSID and incompatible captures prevent recovery. Monitor-mode capability depends on the adapter/driver/VM. Offline analysis requires no deauthentication.

Related: [wireless](../topics/wireless.md), [iw](iw.md). Source: [Aircrack-ng documentation](https://www.aircrack-ng.org/doku.php?id=main).
