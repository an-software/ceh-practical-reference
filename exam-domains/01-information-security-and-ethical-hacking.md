# 1. Information Security and Ethical Hacking

Subdomain: Introduction to Ethical Hacking.

## Basic steps

1. Identify the asset, business purpose and confidentiality, integrity and availability requirements.
2. Confirm written scope: targets, identities, permitted techniques, time window and stop conditions.
3. Distinguish authentication from authorization, threats from vulnerabilities, and technical impact from business risk.
4. Plan discovery, validation, evidence collection and remediation; use the least intrusive method that demonstrates the issue.
5. Record commands, timestamps/timezone, identity, observations and limitations. Preserve originals and hash evidence copies.
6. Report reproducible findings with impact, remediation and retest results; document cleanup and preserve logs.

## Helpful tools

| Tool or resource | Use |
| --- | --- |
| Markdown editor and [Git](../tools/git.md) | Structured notes, change tracking and local search |
| SHA256 / PowerShell [`Get-FileHash`](../tools/get-filehash.md) | Evidence integrity checks |
| Asset/scope checklist | Keep testing within authorized targets and actions |
| Risk matrix and finding template | Prioritize and communicate validated issues |

## Result check

Can another person reproduce the observation from your notes? Does the evidence support the impact claimed? Avoid treating a scanner alert as a confirmed finding.

Related notes: [foundations and reporting](../docs/foundations.md), [practical workflow](../README.md).
