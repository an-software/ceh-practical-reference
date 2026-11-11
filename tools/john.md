# John the Ripper

Priority writeup tool; often called John or John Jumbo. Purpose: offline recovery of authorized lab password hashes.

## Basic workflow

1. Identify the complete hash format, including any salt or application wrapper.
2. Check that the installed build supports the format; select a small lab dictionary.
3. Run recovery, then display and independently verify a result with the same format.

## Example

John Jumbo, using the synthetic fixture from [passwords](../topics/passwords.md):

```bash
john --list=formats
john --format=Raw-MD5 --wordlist=lab-words.txt lab-hashes.txt
john --show --format=Raw-MD5 lab-hashes.txt
```

## Troubleshooting

Core and Jumbo builds differ. No hashes loaded may mean an unsupported/misidentified format. “No password hashes left” can mean results already exist in the potfile.

Source: [John examples](https://www.openwall.com/john/doc/EXAMPLES.shtml).
