# HashCalc

Priority writeup tool. Purpose: GUI calculation of digests/checksums for files or text; not hash-to-password decryption.

## Basic workflow

1. Select **File** as the input type when the task concerns file bytes.
2. Browse to the working-copy file and select the exact algorithm requested.
3. Calculate and compare with a trusted reference using the same algorithm/input.
4. Record the file path, algorithm and digest.

## Example

Hash a synthetic `lab-file.txt` using SHA256 in the GUI. On Windows, independently cross-check:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath .\lab-file.txt
```

Tools in this example: [Get-FileHash](get-filehash.md).

## Troubleshooting

Hashing a path string is different from hashing file contents. Newlines and encodings change bytes. Use MD5 only when a legacy task specifically requests it; digest equality alone does not authenticate an author.

Related: [cryptography](../topics/cryptography.md), [Get-FileHash](get-filehash.md). Vendor reference: [SlavaSoft HashCalc](https://www.slavasoft.com/hashcalc/) (timed out during review; current availability not verified).
