# OpenVAS / Greenbone Vulnerability Management

Priority writeup tool. Purpose: vulnerability scanning and reporting. OpenVAS is associated with the scanner within the broader Greenbone stack; package/UI naming varies.

## Basic workflow

1. Confirm the lab scanner is healthy and its vulnerability feeds are available/current.
2. Define only the authorized target, relevant port list and suitable scan configuration.
3. Run the scoped task; supply scan credentials only where the lab permits authenticated checks.
4. Open the report entry and record host/port, detection details, quality of detection, severity and referenced CVE identifiers.
5. Corroborate the exact CVE against a vendor advisory/CVE record and actual target configuration before reporting it as confirmed.

## Example

In the web UI, create a target for the single lab host, create a task using that target, run it, then inspect its findings and references. Export the minimal report to ignored `evidence/`. UI labels and available scan configurations depend on deployment/version.

## CVE versus CWE

**CVE** identifies a specific publicly cataloged vulnerability, for example the identifier format `CVE-YEAR-NUMBER`. **CWE** classifies a weakness type. Scanner test IDs, CVSS severity scores and Exploit-DB IDs are also different identifiers. Some legitimate findings have no CVE; do not invent one to fill a field.

## Troubleshooting

Missing feeds, incomplete setup, host-discovery filtering or failed scan authentication can produce empty/incomplete results. A banner-based match can be wrong or patched by a backport. Read detection evidence and confidence rather than copying the top severity result.

Related: [SearchSploit](searchsploit.md), [system-hacking domain](../exam-domains/03-system-hacking-phases-and-attack-techniques.md). Sources: [Greenbone Community documentation](https://greenbone.github.io/docs/latest/), [OpenVAS scanner component](https://github.com/greenbone/openvas-scanner), [CWE definition](https://cwe.mitre.org/about/index.html).
