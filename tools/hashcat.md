# Hashcat

Priority writeup tool. Purpose: offline password candidate testing; hashing is not reversible message decoding.

## Basic workflow

1. Establish the hash's exact source format rather than guessing from length.
2. Confirm supported devices and select the correct hash mode and attack mode.
3. Test synthetic/supplied candidates, display matches and verify locally.

## Example

Use the synthetic raw-MD5 fixture in [passwords](../topics/passwords.md), inside ignored evidence storage:

```bash
hashcat -I
hashcat -m 0 -a 0 lab-hashes.txt lab-words.txt --potfile-path lab.potfile
hashcat -m 0 lab-hashes.txt --show --potfile-path lab.potfile
```

## Troubleshooting

`-a 0` uses a dictionary; `-a 3` expects a mask. Raw NTLM (1000) differs from NetNTLMv2 (5600). Token errors suggest a wrong mode/input layout. Exhausted candidates do not prove a password is unrecoverable. Do not force past device/self-test failures.

Sources: [Hashcat](https://github.com/hashcat/hashcat), [example hashes](https://hashcat.net/wiki/doku.php?id=example_hashes).
