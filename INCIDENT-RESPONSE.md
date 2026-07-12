# StatusLens — Security Incident Response Plan

_Last updated: 2026-07-08_

This plan follows Atlassian's guidance for preparing for a security incident
(https://developer.atlassian.com/platform/marketplace/preparing-for-a-security-incident/)
and the Marketplace security bug fix policy.

## 1. Roles

StatusLens is maintained by a solo developer who acts as the security contact,
incident lead, and fix owner.

- Security contact: statuslens.security@en-rai.net
- Reports are also accepted via https://github.com/tori3/statuslens-docs/issues
  (non-sensitive) or privately by email (sensitive).

## 2. Detection and intake

Potential incidents are identified from:

- Reports to the security contact email
- Atlassian Marketplace security notifications / vulnerability reports
- Forge platform alerts and application error logs

Every report is acknowledged within 3 business days.

## 3. Triage and severity

The incident lead assesses impact and assigns a severity (Critical / High /
Medium / Low) based on the CVSS score and the data or functionality affected,
consistent with Atlassian's Marketplace Bug Fix Policy timelines.

## 4. Containment and remediation

Because StatusLens runs entirely on Atlassian Forge with no external
infrastructure and no stored issue content, containment focuses on the app code:

1. Reproduce and confirm the issue in the development environment.
2. Develop and test a fix (unit tests + lint must pass).
3. Deploy the fix to production via `forge deploy -e production`. Forge pushes
   the new version to all installations automatically.
4. If needed as a temporary measure, coordinate with Atlassian to restrict the
   affected version.

Target remediation times follow the Marketplace Bug Fix Policy
(Critical: as fast as possible; per Atlassian's published SLAs by severity).

## 5. Notification

- **Atlassian**: notified promptly for any critical vulnerability or confirmed
  security incident, using Atlassian's notification templates.
- **Affected customers**: notified in line with Atlassian's Security Incident
  Notification guidelines and applicable data-protection obligations.

Because the app stores no issue content and performs no external egress, the
scope of any data exposure is inherently limited to filter settings and
short-lived aggregate cache held within Atlassian Forge storage.

## 6. Post-incident review

After resolution, the incident lead documents the root cause, the fix, and any
preventive follow-ups (e.g., added tests, dependency updates), and updates this
plan if needed.

## References

- Preparing for a security incident: https://developer.atlassian.com/platform/marketplace/preparing-for-a-security-incident/
- Security bug fix policy: https://developer.atlassian.com/platform/marketplace/security-bugfix-policy/
- Incident management guidelines: https://developer.atlassian.com/platform/marketplace/app-security-incident-management-guidelines/
