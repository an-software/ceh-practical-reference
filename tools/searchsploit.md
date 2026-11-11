# SearchSploit

Priority writeup tool. Purpose: search a local Exploit-DB index for matching vulnerability references.

## Basic workflow

1. Gather the exact product, version, platform and observed behavior.
2. Search for related entries and read their prerequisites/references.
3. Corroborate the claimed CVE with the vendor advisory or CVE record and target patch status.

## Example

```bash
searchsploit 'EXACT PRODUCT VERSION'
searchsploit --nmap evidence/services.xml
```

## Troubleshooting

An Exploit-DB entry number is not a CVE number. Search results are candidates, not confirmation of exploitability. Old indexes miss newer entries; backported fixes make version-only conclusions unreliable. This workflow does not execute results.

Related: [OpenVAS](openvas.md), [reconnaissance](../topics/reconnaissance.md). Source: [SearchSploit manual](https://www.exploit-db.com/searchsploit).
