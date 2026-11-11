# OWASP ZAP / ZAP

Priority writeup tool. Purpose: intercepting proxy, passive web analysis and scoped active application testing.

## Basic workflow

1. Start with an isolated lab browser/profile and scope the intended site/context.
2. Browse the application through the proxy; establish authenticated baseline requests.
3. Review passive alerts and compare requests/responses manually.
4. If authorized, select a narrow active test; validate the finding and export minimal evidence.

## Example

Use the manual exploration/browser workflow, open a synthetic lab page and inspect the History/Alerts views. Keep sessions and reports under ignored evidence storage. Configure authentication before interpreting protected-page coverage.

## Troubleshooting

Active scanning sends test payloads and can change application state. Untrusted proxy certificates, wrong ports and expired sessions can cause misleading failures. An alert is not proof of exploitability.

Related: [web testing](../topics/web-testing.md), [Burp Suite](burp-suite.md). Source: [ZAP getting started](https://www.zaproxy.org/docs/desktop/start/).
