<p align="center">
  <img src="assets/statuslens-logo-256.png" width="128" alt="StatusLens logo" />
</p>

<h1 align="center">StatusLens – Time in Status for Jira</h1>

<p align="center">
  See where work gets stuck — time in status for every Jira issue and project.
</p>

---

[日本語版はこちら / Japanese version](README.ja.md)

StatusLens visualizes how long your Jira issues spend in each status, built on Atlassian Forge.

- **Issue panel** — per-status time for the issue you're viewing
- **Project report** — issues × statuses table with per-status averages
- **CSV export** — UTF-8 with BOM, Excel-friendly
- **Japanese / English UI** — follows each user's Jira language setting

> 🔒 **Privacy**: your issue data never leaves Atlassian's infrastructure.
> StatusLens stores only filter settings and an aggregate cache that expires
> after 15 minutes — no external servers involved. See [PRIVACY.md](PRIVACY.md)
> for details.

## Using the issue panel

1. Open any issue
2. Click the **apps icon next to the "+" button** under the issue title
3. Select **StatusLens: Time in Status**

Time is aggregated across round trips (e.g., an issue that bounced back to
In Review twice), and the current status keeps counting until now.

## Using the project report

1. In your project's tab bar, choose **More** → **StatusLens: Time in Status**
2. Set filters and hit **Run report**
   - **Additional JQL** (optional), **date range** (created/resolved based), and **statuses**
3. Review the issues × statuses table with the **average row** (up to 500 issues)
4. **Download CSV** — includes both human-readable durations and raw seconds

Filters are saved per project and restored on your next visit.

## FAQ

**Q. What permissions does it need?**
Only `read:jira-work` (read issues and changelogs) and `storage:app` (save settings/cache).

**Q. Where is my data stored?**
Issue data is never stored. Only filter settings and a 15-minute aggregate cache
are kept in Atlassian Forge storage. No external servers.

**Q. How is time in status calculated?**
From the issue changelog: duration = next transition time − status entry time.
The current status counts up to now, and repeated visits are summed.

## Support

- 🐛 Bugs & feature requests: [GitHub Issues](https://github.com/tori3/statuslens-docs/issues)
- ✉️ Email: statuslens.security@en-rai.net
- Support languages: Japanese / English
