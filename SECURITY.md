# Security Policy

This policy applies to every repository in the [Elastic Email organization](https://github.com/ElasticEmail) that doesn't have its own `SECURITY.md`.

## Supported versions

Security fixes are released for the latest published version of each SDK, tool and integration. Please upgrade to the latest version before reporting an issue.

The legacy `ElasticEmail.WebApiClient-*` repositories (Web API v2) are archived and no longer receive security fixes. Please move to the current v4 SDKs.

## Reporting a vulnerability

**Please do not open a public GitHub issue for security vulnerabilities.**

Email **integrations@elasticemail.com** with the subject `Security: <repository name>`.

Please include:

- The affected repository and version(s)
- A description of the issue and its impact
- Steps to reproduce, or a proof of concept

We will acknowledge your report, investigate, and keep you updated on the fix. Please give us reasonable time to release a fix before disclosing the issue publicly.

## API key safety

If you think an API key has been exposed (in a commit, log, issue or screenshot), revoke it right away in your [Elastic Email API settings](https://app.elasticemail.com/marketing/settings/new/manage-api) and create a new one.
