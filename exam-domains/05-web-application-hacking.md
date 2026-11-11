# 5. Web Application Hacking

Subdomains: Hacking Web Servers; Hacking Web Applications; SQL Injection.

## Basic steps

1. Identify the correct host header, protocol, port, application base path and authentication requirements.
2. Map routes, parameters, forms, uploads, technologies and roles. Establish baseline responses for valid and nonexistent paths.
3. Review server configuration, exposed files, error disclosure, TLS, security headers and cookie settings.
4. Test authorization with two synthetic roles/accounts. Change one input at a time and compare expected access with actual results.
5. For SQLi, identify the parameter and use controlled response comparisons; in the lab, progress from database discovery to the minimum required table/column evidence.
6. Review upload handling and command-injection behavior with inert files or harmless identity commands in an intentionally vulnerable lab.
7. Record the exact request, authenticated context, evidence and remediation; redact secrets and keep captured sessions outside Git.

## Helpful tools

| Tool | Use |
| --- | --- |
| [Browser developer tools](../tools/browser-devtools.md), [curl](../tools/curl.md) | HTTP requests, headers, redirects, cookies and TLS checks |
| [Burp Suite](../tools/burp-suite.md), [OWASP ZAP](../tools/owasp-zap.md) | Proxy inspection, request comparison and scoped testing |
| [ffuf](../tools/ffuf.md), [Gobuster](../tools/gobuster.md), [Dirb](../tools/dirb.md) | Small, rate-controlled content-discovery lists |
| [Nikto](../tools/nikto.md) | Web-server configuration leads requiring validation |
| [WPScan](../tools/wpscan.md) | WordPress users/components and vulnerability references |
| [sqlmap](../tools/sqlmap.md) | Parameter-specific SQLi testing with a saved lab request |
| [OWASP WSTG](../tools/owasp-wstg.md) | Test organization and coverage checklist |

## Result check

Wildcard routes can return 200 for nonexistent paths. Redirects and expired cookies can invalidate comparisons. Object-ID tampering tests IDOR/BOLA; SSRF means the server makes an input-influenced request. A scanner alert or HTTP 302 alone is not proof.

Related notes: [web testing commands](../topics/web-testing.md), [bounded password tests](../topics/passwords.md), [OWASP WSTG](https://github.com/OWASP/wstg).
