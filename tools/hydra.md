# Hydra

Priority writeup tool. Purpose: online authentication testing against explicitly authorized lab services.

## Basic workflow

1. Identify the service, one synthetic account and account-lockout/request limits.
2. Start with a tiny supplied candidate list and low concurrency.
3. Validate any reported success by signing in and checking the actual identity/access.

## Example

```bash
hydra -l labuser -P lab-small.txt -t 1 -f ftp://192.0.2.10
hydra -U http-post-form
```

`-l` selects one user, `-L` a username file, `-P` a password file. HTTP form modules need exact field names, session handling and reliable response markers.

## Troubleshooting

An HTTP redirect is not proof of success. CSRF tokens, cookies, protocol support and lockouts can invalidate a run. Check the actual server response before increasing attempts.

Related: [passwords](../topics/passwords.md). Source: [Hydra upstream](https://github.com/vanhauser-thc/thc-hydra).

