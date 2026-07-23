# Privacy Policy — Assets Exporter for Jira Service Management

**Effective date: 23 July 2026 · Vendor: Schema Tools**

## Summary

Assets Exporter runs entirely on Atlassian Forge, inside Atlassian's
infrastructure. **We do not operate any servers, and your data never leaves
Atlassian.**

## What the app accesses

To produce an export, the app reads, via Atlassian's APIs, with permissions
granted at installation:

- Assets object schemas, object types, attribute definitions and objects
  (read-only);
- and writes exactly one thing: the generated Excel workbook, attached to the
  Jira issue you choose.

## What we collect

**Nothing.** The app has no external backend, no analytics, no tracking, and
makes no network calls outside Atlassian. Export job state (progress counters,
never your Assets data content beyond what a running export needs) is held
temporarily in Forge storage, hosted by Atlassian, and is not accessible to us.

## Data retention

Generated workbooks live as attachments on your Jira issues, under your
existing Jira permissions and retention rules. We hold no copies. Uninstalling
the app removes its Forge storage per Atlassian's platform policy.

## Third parties

None. The app is eligible for Atlassian's "Runs on Atlassian" programme, which
requires that no data egresses Atlassian's infrastructure.

## Contact

Questions: see the support contact on the Marketplace listing.

## Changes

We will update this page and the effective date if the app's data behaviour
ever changes; material changes will also be noted in the version release notes.
