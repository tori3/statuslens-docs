# Security Policy

## Reporting a vulnerability

If you discover a security issue in StatusLens, please report it privately:

- Email: statuslens.security@en-rai.net (subject: "SECURITY: StatusLens")
- Please do not open a public GitHub issue for security reports

We aim to acknowledge reports within 3 business days and to release a fix as
quickly as possible depending on severity.

## Scope and architecture

StatusLens is an Atlassian Forge app:

- Runs entirely on Atlassian's infrastructure — no vendor-operated servers
- No external egress: the app never sends data outside Atlassian
- Scopes: `read:jira-work`, `storage:app` only
- Stored data: per-project filter settings and a 15-minute aggregate cache in
  Atlassian Forge storage. Issue content is never stored
- No PATs, passwords, or shared secrets are collected from users

## Supported versions

Only the latest version published on the Atlassian Marketplace is supported.
