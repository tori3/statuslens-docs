# StatusLens – Data Security and Privacy Statement

_Last updated: 2026-07-15_

[日本語版はこちら / Japanese version](PRIVACY.ja.md)

StatusLens runs entirely on the Atlassian Forge platform. **No data is ever sent to
or stored outside Atlassian's infrastructure** (zero external egress).

## What we store

| Data | Location | Retention |
|---|---|---|
| Report filter settings (JQL, date range, status selection) | Atlassian Forge Storage (per project) | Until changed by the user |
| Report result cache (issue keys and per-status duration seconds) | Atlassian Forge Storage | 15 minutes (TTL) |

## What we do NOT store

- Issue content (summaries, descriptions, comments, attachments) is **never stored** —
  it is fetched from the Jira API on each view
- No personal data (names, email addresses, etc.) is collected or stored
- No cookies, external analytics, or tracking of any kind

## Permissions (scopes)

- `read:jira-work` — read issues and changelogs to calculate time in status
- `storage:app` — store the filter settings and cache described above

## Contact

Questions about data handling: statuslens.security@en-rai.net or
[GitHub Issues](https://github.com/tori3/statuslens-docs/issues).
