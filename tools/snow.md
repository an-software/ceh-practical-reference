# SNOW

Priority writeup tool; also distributed as `stegsnow` on some systems. Purpose: hide/extract data in trailing whitespace in text.

## Basic workflow

1. Preserve the exact original bytes; avoid editors that trim tabs/spaces or convert line endings.
2. Identify whether the lab data is password-protected and compressed.
3. Extract using the matching password/settings; save output separately.

## Example

Illustrative legacy SNOW CLI; check your installed binary's help. This example requires a compressed, password-protected lab input:

```bash
snow -C -p 'LAB_PASSWORD' lab-text.txt
```

## Troubleshooting

Whitespace normalization can destroy the carrier. Compression/password options must match the embedded data. Windows may name the program `snow.exe`; Linux packaging may use `stegsnow`. SNOW does not extract arbitrary hidden image payloads. Command-line passwords can enter shell history.

Related: [forensics](../topics/forensics.md). References: [SNOW upstream](https://www.darkside.com.au/snow/) (not retrievable in this review), [Kali stegsnow package/help](https://www.kali.org/tools/stegsnow/) (checked as a fallback). On Kali substitute `stegsnow` for `snow` in the example.
