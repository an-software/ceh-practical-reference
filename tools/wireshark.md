# Wireshark

Priority writeup tool. Purpose: inspect captured traffic, streams, endpoints and protocol behavior.

## Basic workflow

1. Open a working copy of the lab capture; note timezone, duration and capture position.
2. Review Statistics → Protocol Hierarchy, Endpoints and Conversations.
3. Apply a display filter, inspect relevant frames and follow the corresponding stream.
4. Correlate identities/timestamps and save only the required evidence.

## Examples

Display filters, not capture-filter syntax:

```text
ip.addr == 192.0.2.10
http.request.method == "POST"
tcp.flags.syn == 1 && tcp.flags.ack == 0
dns.flags.response == 0
```

## Troubleshooting

TLS payloads require appropriate decryption material. POST alone does not prove credentials are exposed. Many SYNs alone do not prove DoS. Numeric “bit” questions need the exact protocol field and numbering convention.

Related: [forensics](../topics/forensics.md), [tshark](tshark.md). Source: [Wireshark documentation](https://www.wireshark.org/docs/).

