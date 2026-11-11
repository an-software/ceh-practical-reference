# Wireless

Keywords: Wi-Fi WPA WPA2 capture monitor mode [Aircrack-ng](../tools/aircrack-ng.md) adapter.

Use an isolated lab AP and supplied captures. Identify adapter, driver, channel and BSSID. Passive capture also requires authorization for the network involved.

```bash
iw dev
iw list
ip link
# Inspect a supplied capture without transmitting:
capinfos lab-wifi.cap
# Offline lab WPA/WPA2-Personal recovery:
aircrack-ng -w lab-words.txt -b 02:00:00:00:00:01 lab-wifi.cap
```

Tools in this example: [Aircrack-ng](../tools/aircrack-ng.md), [capinfos](../tools/capinfos.md), [ip (iproute2)](../tools/ip.md), [iw](../tools/iw.md).

Replace the example BSSID with your lab AP. Captures need suitable authentication material. WPA3 and enterprise authentication require different workflows. This workflow needs no deauthentication or injection.

Troubleshooting: WSL often lacks direct monitor-mode adapter access; use Linux or an appropriate VM with USB passthrough. Managed mode differs from monitor mode. Missing handshakes, wrong AP/channel and weak signal affect results. Restore normal network settings after lab use.

Sources: [Aircrack-ng](https://github.com/aircrack-ng/aircrack-ng), [documentation](https://www.aircrack-ng.org/doku.php?id=main).

## Supplied capture exercises

The imported root guide includes a rogue-AP/password-recovery scenario. Treat the capture's SSID/BSSID and authentication type as evidence, not a ready-made answer. In [Wireshark](../tools/wireshark.md), inspect `wlan` management frames and `eapol` authentication traffic, correlate the client with the intended AP, then use the offline lab workflow above if the capture and protocol support it. Similar SSIDs alone do not establish a rogue AP.

IoT traffic may use MQTT or other application protocols over ordinary wired/Wi-Fi transport; inspect the actual decoded protocol rather than assuming all IoT messages are wireless encryption problems. Use [packet analysis](forensics.md) for conversations and payload inspection. The imports supply little additional wireless procedure; adapter setup and the upstream [Aircrack-ng](../tools/aircrack-ng.md) manual remain the primary references.
