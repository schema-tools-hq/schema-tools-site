# Security & Incident Response — Schema Tools

## Security posture

Assets Exporter runs entirely on Atlassian Forge. There are no vendor-operated
servers, no data egress outside Atlassian, no stored credentials or tokens, and
the vendor never receives or processes customer data. Encryption at rest and in
transit is provided by the Atlassian platform.

Development practices: every release passes an automated test suite and strict
TypeScript type checking; dependencies are audited (`npm audit`) before release;
source code access requires multi-factor authentication.

## Reporting a vulnerability

Email **support@sixwiki.com** with subject "SECURITY". Include reproduction
steps if possible. We acknowledge security reports within **48 hours**.

## Incident response plan

We follow Atlassian's Marketplace incident guidelines
(developer.atlassian.com/platform/marketplace/preparing-for-a-security-incident/):

1. **Assess & contain** — reproduce the report, determine scope and severity
   (CVSS), and if a fix requires it, disable the affected code path via a
   platform release.
2. **Fix** — patch within the timelines of Atlassian's Security Bug Fix Policy
   (critical vulnerabilities prioritised ahead of all other work).
3. **Notify** — report the vulnerability to Atlassian via their vulnerability
   management process (AMS on ecosystem.atlassian.net) and notify affected
   customers using Atlassian's notification templates when the incident
   requires it.
4. **Review** — post-incident, document the root cause and the change that
   prevents the class of issue, not just the instance.

## Data handling

See the [privacy policy](privacy.html). Summary: End-User Data is read from
Assets and written to a Jira attachment inside the customer's own Atlassian
instance; transient export job state lives in Forge storage and nowhere else.
