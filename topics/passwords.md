# Passwords

Keywords: offline hashes [Hashcat](../tools/hashcat.md) dictionary wordlist recovery potfile.

Use hashes supplied by or collected within the authorized lab. Identify the actual format before choosing a mode. Prefer offline recovery over online guessing.

```bash
hashcat --help
hashcat -I
# Synthetic fixture; MD5 is unsuitable for password storage:
printf 'labpass' | md5sum | cut -d ' ' -f1 > lab-hashes.txt
printf 'example\nlabpass\n' > lab-words.txt
hashcat -m 0 -a 0 lab-hashes.txt lab-words.txt --potfile-path lab.potfile
hashcat -m 0 lab-hashes.txt --show --potfile-path lab.potfile
```

Tools in this example: [Hashcat](../tools/hashcat.md), [md5sum](../tools/md5sum.md).

Mode 0 is raw MD5 only. Salted hashes, NTLM and application formats need their own modes and input layouts. Keep recovered passwords and potfiles out of commits; run these commands in ignored `evidence/`.

Troubleshooting: “token length exception” often means a wrong mode or malformed input. “No devices found” needs supported drivers/runtime setup; do not force past self-test failures. Exhausting a wordlist means no candidate matched, not that recovery is impossible.

Sources: [Hashcat](https://github.com/hashcat/hashcat), [example hashes](https://hashcat.net/wiki/doku.php?id=example_hashes).

## [John](../tools/john.md), modes and wordlists

```bash
# John Jumbo build; verify available formats locally:
john --list=formats
john --format=Raw-MD5 --wordlist=lab-words.txt lab-hashes.txt
john --show --format=Raw-MD5 lab-hashes.txt
# Explicit raw NTLM offline lab input:
hashcat -m 1000 -a 0 lab-ntlm.txt lab-words.txt --potfile-path lab.potfile
```

Tools in this example: [Hashcat](../tools/hashcat.md), [John the Ripper](../tools/john.md).

| [Hashcat](../tools/hashcat.md) mode | Input type |
| --- | --- |
| 0, 100, 1400 | Raw MD5, SHA1, SHA256 |
| 900, 1000 | Raw MD4, NTLM |
| 1800, 3200 | sha512crypt, bcrypt |
| 5600 | NetNTLMv2 challenge/response, not a raw NTLM hash |

Hash identification tools give candidates rather than certainty. Mode 110, for example, has a specific SHA1 salt layout; “SHA1 with salt” alone is insufficient. Copy the full format from the upstream example-hash reference. `-a 0` is a wordlist attack; `-a 3` expects a mask, not a wordlist path. `--show` displays prior results and does not start cracking. Optimized kernels (`-O`) may impose password-length limits.

[SecLists](../tools/seclists.md), lab-provided dictionaries and small [CeWL](../tools/cewl.md) lists serve different purposes. Do not assume [RockYou](../tools/rockyou.md) exists or is decompressed. Rainbow tables precompute hash chains and are most applicable to matching unsalted formats; unique salts substantially reduce reuse. [Ophcrack](../tools/ophcrack.md)/[RainbowCrack](../tools/rainbowcrack.md) need tables for the exact target format.

## Bounded online lab authentication

Use a small synthetic candidate list and check account-lockout limits first. For a single lab FTP account:

```bash
hydra -l labuser -P lab-small.txt -t 1 -f ftp://192.0.2.10
hydra -U http-post-form
```

Tools in this example: [Hydra](../tools/hydra.md).

[Hydra](../tools/hydra.md) `-l` is one username; `-L` is a file of usernames. SSH URLs use `ssh://`, not `ssh:`. HTTP forms require the correct path, field names, cookies/CSRF behavior and a reliable failure/success marker. [Burp Intruder](../tools/burp-suite.md) can test one marked password field with Sniper; Cluster bomb creates the Cartesian product of lists and can greatly increase requests. A 302 is not proof of valid credentials: compare session state and authenticated content.

[Responder](../tools/responder.md) challenge/response logs are an offline format-analysis exercise here: use the lab-supplied capture and select NetNTLMv2 rather than raw NTLM. Active name-service poisoning changes other hosts' authentication traffic and is a separate scoped lab activity. Avoid submitting real hashes or passwords to online cracking sites; the supplied links remain in the source catalog for provenance.

Additional sources: [John examples](https://www.openwall.com/john/doc/EXAMPLES.shtml), [Hydra](https://github.com/vanhauser-thc/thc-hydra).
