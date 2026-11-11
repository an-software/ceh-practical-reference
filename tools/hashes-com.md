# Hashes.com

Priority writeup service, not a local executable. Purpose: look up candidate plaintexts in an already-recovered-hash database and use related hash utilities.

## Basic workflow

1. Identify the lab's algorithm and whether external submission is explicitly allowed.
2. Use only synthetic/non-sensitive examples for an online lookup; prefer local [John](john.md)/[Hashcat](hashcat.md) for confidential material.
3. If a candidate is returned, calculate its hash locally using the same algorithm and exact byte encoding.
4. Record whether the result is a verified match, ambiguous format or no database hit.

## Example

Use the public synthetic fixture from [passwords](../topics/passwords.md) when evaluating a lookup. Never upload a production hash file or credential capture merely because a writeup used a website.

## Troubleshooting

Hash lookup is not mathematical decryption. No result means the service did not return a known match, not that recovery is impossible. Hash-only format identification may be ambiguous; salts and input encoding matter. Do not treat a found plaintext as proof it is an authorized account credential without validation.

Related: [Hashcat](hashcat.md), [John](john.md), [CrackStation](crackstation.md). Source: [Hashes.com lookup description](https://hashes.com/en/decrypt/hash).
