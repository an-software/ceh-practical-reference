# Cryptography

Keywords: [OpenSSL](../tools/openssl.md) SHA256 Base64 certificate PEM DER TLS encryption.

Encoding is reversible representation; hashing produces a digest; encryption requires a key. Integrity and authenticity are separate questions.

```bash
openssl version
openssl dgst -sha256 sample.bin
printf 'lab example' | openssl base64 -A
printf 'bGFiIGV4YW1wbGU=' | openssl base64 -d -A
openssl x509 -in lab-cert.pem -noout -subject -issuer -dates -fingerprint -sha256
openssl s_client -connect 192.0.2.10:443 -servername lab.example \
  -CAfile lab-ca.pem -verify_hostname lab.example -verify_return_error </dev/null
```

Tools in this example: [OpenSSL](../tools/openssl.md).

Record hostname, certificate validity, issuer and verification result. Bare `s_client` output does not establish that trust was verified. Keep private keys and decrypted secrets outside commits.

Troubleshooting: PEM has textual BEGIN/END markers; binary DER may need `-inform DER`. Base64 failures may involve padding/newlines. TLS errors can reflect a wrong clock, incorrect SNI hostname or incomplete certificate chain.

Sources: [OpenSSL](https://github.com/openssl/openssl), [official manuals](https://docs.openssl.org/).

## Integrity comparisons and supplied GUI tools

Windows PowerShell:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath .\original.txt,.\working.txt
Get-ChildItem .\evidence -File | Get-FileHash -Algorithm SHA256
# Only when a legacy lab explicitly asks for MD5:
Get-FileHash -Algorithm MD5 -LiteralPath .\lab-file.txt
```

Tools in this example: [Get-FileHash](../tools/get-filehash.md).

A digest mismatch establishes different bytes, not who changed them. Equal MD5 digests are not a modern authenticity guarantee. [HashCalc](../tools/hashcalc.md), [HashMyFiles](../tools/hashmyfiles.md) and checksum GUIs can calculate the requested digest; distinguish checksums from encryption and choose the exact algorithm.

For a [VeraCrypt](../tools/veracrypt.md) lab container, preserve its original hash, select the existing container, choose a free mount point/drive, mount read-only where possible, enter only the supplied credentials/keyfiles, inspect the needed file and dismount afterward. Do not create or format a volume over the evidence file. Wrong password errors can also indicate wrong PIM/keyfiles or a damaged container.

[CrypTool](../tools/cryptool.md) exercises require the exact cipher, mode (such as legacy 3DES/ECB), key bytes, encoding and padding. 3DES is symmetric; the source's placement under “asymmetric” is incorrect. Repeated `11` values in one anecdote are scenario-specific, not universal keys. ECB and 3DES are legacy study examples rather than new-design recommendations. [BCTextEncoder](../tools/bctextencoder.md) and [OpenStego](../tools/openstego.md) use distinct file formats; select the matching tool instead of treating them as interchangeable decoders.

For rainbow tables and password formats see [passwords](passwords.md); for [SNOW](../tools/snow.md)/[OpenStego](../tools/openstego.md)/[Steghide](../tools/steghide.md) see [forensics](forensics.md).
