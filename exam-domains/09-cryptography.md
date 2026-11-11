# 9. Cryptography

Subdomain: Cryptography.

## Basic steps

1. Determine whether the task concerns encoding, hashing, encryption, certificate validation or hidden data; these require different methods.
2. Preserve a working copy and record the original file's SHA256. Identify the format, algorithm and required output.
3. For integrity tasks, calculate the requested digest and compare against a trusted reference; document differing bytes without guessing who changed them.
4. For encryption exercises, establish cipher, mode, key/password, key encoding, IV and padding from the lab instructions.
5. For certificates/TLS, inspect subject/hostname, issuer, validity and chain verification using the correct hostname and lab CA.
6. For password hashes, choose the exact offline recovery format. For steganography, select the correct image/text container tool instead of treating it as a generic cipher.
7. Save minimal results, dismount opened containers and keep keys, passphrases and plaintext secrets outside Git.

## Helpful tools

| Tool | Use |
| --- | --- |
| [OpenSSL](../tools/openssl.md) | Digests, Base64, certificate inspection and TLS verification |
| [sha256sum](../tools/sha256sum.md) / PowerShell [`Get-FileHash`](../tools/get-filehash.md) | File integrity comparison |
| [VeraCrypt](../tools/veracrypt.md) | Open a supplied encrypted container, preferably read-only |
| [CrypTool](../tools/cryptool.md) | Visualize cipher operations and complete specified legacy lab exercises |
| [HashCalc](../tools/hashcalc.md), [HashMyFiles](../tools/hashmyfiles.md) | GUI digest calculation where required |
| [John Jumbo](../tools/john.md), [Hashcat](../tools/hashcat.md) | Offline lab password-hash recovery |
| [Steghide](../tools/steghide.md), [OpenStego](../tools/openstego.md), [SNOW](../tools/snow.md) | Related hidden-data tasks; distinct from cryptographic decryption |

## Result check

Hash identification may be ambiguous. Digest equality does not by itself establish authenticity. 3DES is symmetric and legacy; anecdotal keys are not reusable assumptions. Wrong file format, key encoding or padding may explain decryption failure.

Related notes: [cryptography commands](../topics/cryptography.md), [password formats](../topics/passwords.md), [hidden data](../topics/forensics.md), [OpenSSL manuals](https://docs.openssl.org/).
