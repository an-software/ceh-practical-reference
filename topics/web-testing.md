# Web testing

Keywords: HTTP HTTPS cookies headers proxy directory discovery OWASP validation.

Map routes and authentication boundaries. Inspect lab requests with a proxy, vary one input at a time and compare status, length and content. Use [OWASP WSTG](../tools/owasp-wstg.md) cases to structure evidence.

```bash
mkdir -p evidence
curl -sS -D evidence/headers.txt -o evidence/body.html http://192.0.2.10/
curl -sS -I http://192.0.2.10/robots.txt
curl --resolve lab.example:80:192.0.2.10 http://lab.example/
# Supply a small lab-specific paths.txt wordlist:
ffuf -u http://192.0.2.10/FUZZ -w paths.txt -rate 10 -mc all -o evidence/paths.json
```

Tools in this example: [curl](../tools/curl.md), [ffuf](../tools/ffuf.md).

Check cookie Secure/HttpOnly/SameSite attributes, authorization per role, input handling and error disclosure. A missing header is not automatically exploitable. Keep authenticated cookies outside Git.

Troubleshooting: wildcard routes may return 200 for nonexistent paths; request a random path as a baseline. TLS errors may mean the wrong hostname or missing lab CA: use `--cacert lab-ca.pem`. Redirects may require the correct virtual host. A 403 alone is not proof that a directory exists.

Sources: [OWASP WSTG](https://github.com/OWASP/wstg), [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings), [curl](https://curl.se/docs/manpage.html), [ffuf](https://github.com/ffuf/ffuf).

## Content discovery, WordPress and scanners

```bash
gobuster dir -u http://192.0.2.10/ -w paths.txt -t 5 -x php,html,txt
dirb http://192.0.2.10/ paths.txt
nikto -h http://192.0.2.10/
wpscan --url http://192.0.2.10:8080/CEH/ --enumerate u
cewl -d 1 -m 5 -w evidence/lab-words.txt http://192.0.2.10/
```

Tools in this example: [CeWL](../tools/cewl.md), [Dirb](../tools/dirb.md), [Gobuster](../tools/gobuster.md), [Nikto](../tools/nikto.md), [WPScan](../tools/wpscan.md).

Keep the WordPress subdirectory and port correct. [WPScan](../tools/wpscan.md) vulnerability metadata may require an API token; do not commit it. [ZAP](../tools/owasp-zap.md)/[Burp](../tools/burp-suite.md) active scanners generate requests and can change application state; scope the target and begin with passive inspection. Do not assume that an alert establishes exploitability.

## SQL injection workflow

SQLi families in the supplied guide include UNION, error-based, boolean blind, time blind, out-of-band and second-order injection. Response differences need a stable baseline; timing alone may be network jitter. Stored procedures do not automatically prevent injection if they construct unsafe SQL.

For a disposable intentionally vulnerable lab, save a complete request as ignored `evidence/request.txt`, including the current authenticated session, and select the tested parameter explicitly:

```bash
sqlmap -r evidence/request.txt -p id --dbs
sqlmap -r evidence/request.txt -p id -D labdb --tables
sqlmap -r evidence/request.txt -p id -D labdb -T lab_users --columns
# Retrieve only the synthetic columns required by the lab:
sqlmap -r evidence/request.txt -p id -D labdb -T lab_users -C username --dump
```

Tools in this example: [sqlmap](../tools/sqlmap.md).

Keep `--dbs` inside the command, not after an unquoted shell semicolon. [SQLmap](../tools/sqlmap.md) database/table/column switches are `-D`, `-T`, `-C`; schema names must match actual output. Re-capture expired cookies or CSRF tokens. Database access does not guarantee that `--os-shell` will work; that feature additionally depends on database privileges and platform configuration.

For direct database access using supplied lab credentials:

```bash
mysql -h 192.0.2.10 -u labuser -p
```

Tools in this example: [MySQL client](../tools/mysql.md).

Enter the password at the prompt. In the SQL client use `SHOW DATABASES;`, `USE labdb;`, `SHOW TABLES;` and `DESCRIBE lab_users;`. MySQL `-P` selects a port, not a password; `-u` selects a user.

## DVWA and authorization checks

In a disposable DVWA lab, a command-injection proof can use a harmless identity command, such as `127.0.0.1 | whoami`, then compare output to a valid baseline. Shell separators and quoting differ on Windows/Linux and by security level. Never copy the source's spaced `& &` as though it were `&&`.

For upload testing, compare extension, MIME declaration and file signature using inert files; confirm server-side validation and that uploads cannot execute. A renamed JPEG/PHP example in old notes is a bypass scenario, not an upload security fix. Keep any lab artifacts isolated and remove them afterward.

Changing `id=1` to `id=2` while checking whether another user's object becomes readable tests object-level authorization (IDOR/BOLA). SSRF instead makes the server issue requests to a destination influenced by input. Test two synthetic accounts and record expected versus actual access.

Additional sources: [SQLmap usage](https://github.com/sqlmapproject/sqlmap/wiki/Usage), [WPScan](https://github.com/wpscanteam/wpscan).
