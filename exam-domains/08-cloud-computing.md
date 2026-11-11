# 8. Cloud Computing

Subdomain: Cloud Computing.

## Basic steps

1. Identify the provider, service model (IaaS/PaaS/SaaS), account/tenant/project, region and shared-responsibility boundary.
2. Confirm the authorized lab identity and scope before querying resources. Use supplied credentials without adding them to Git.
3. Inventory relevant identities/roles, storage, workloads, network exposure and logging using read-only views where possible.
4. Review permissions, trust relationships, public access, security-group/firewall rules, secrets handling, encryption configuration and audit coverage.
5. Validate one exposure with a minimal synthetic object or permitted read action. Record both the configuration and the observed access result.
6. Explain the impact and least-privilege/configuration fix, then retest. Remove only explicitly created lab resources and check for ongoing costs.

## Helpful tools

| Tool | Use |
| --- | --- |
| Provider console | Inspect lab account context, IAM, resource policies and audit logs |
| [AWS CLI](../tools/aws-cli.md) | Query authorized AWS services and account resources |
| [Azure CLI](../tools/azure-cli.md) ([`az`](../tools/azure-cli.md)) | Query authorized Azure subscriptions, identities and resources |
| [Google Cloud CLI](../tools/gcloud.md) ([`gcloud`](../tools/gcloud.md)) | Query authorized Google Cloud projects and resources |
| Browser/[curl](../tools/curl.md) | Validate scoped application or synthetic public-object access |
| Policy/IaC files and JSON viewer | Review explicit permissions, trust and network settings |

Choose the provider's tool for the lab rather than installing every SDK. Prefer read-only commands; CLI tools can also create, change and delete resources.

## Result check

Wrong accounts, regions or projects can produce misleading empty results. Access denied can mean limited visibility, not an absent resource. “Public endpoint” and “publicly readable data” are different findings. Do not probe cloud metadata endpoints or other tenants unless that exact activity is in scope.

Related notes: [foundations and reporting](../docs/foundations.md), [web testing](../topics/web-testing.md). Official tool references: [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html), [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/), [Google Cloud SDK](https://cloud.google.com/sdk/docs).
