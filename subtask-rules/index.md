# Subtask Rules — Documentation

A Jira project setting that controls which subtask types are allowed under
each parent work item type — enforced at creation by a Jira workflow
validator, not just hidden in a picker.

## What it does

Jira's issue type schemes control which types exist in a project, but not
which subtask types make sense under which parent: any subtask type can go
under any parent work item. Subtask Rules closes that gap with a per-project
rules matrix:

- **Per-parent-type allow-list** — for each parent type (Task, Story, Bug,
  ...), choose exactly which subtask types are allowed underneath it. Parent
  types you don't touch stay fully unrestricted.
- **Blocked at the source** — enforcement lives in a Jira workflow validator
  on the Create transition, so it is not a client-side filter that Automation
  rules or the REST API can bypass: they hit the same block.
- **Clear deny message** — *"Subtask type X is not allowed under Y (Subtask
  Rules)"*, shown wherever the create attempt happens (issue view form, REST
  API error response).
- **Instant on/off** — an Enabled switch disables enforcement without losing
  your saved matrix.

## Getting started

1. Install the app from the Atlassian Marketplace.
2. Open a company-managed Jira project → **Project settings** → **Subtask
   Rules**.
3. In the matrix, tick the subtask types allowed under each parent type.
   Rows you leave untouched stay unrestricted.
4. Turn **Enabled** on and **Save**. Enabling attaches the validator to the
   project's workflow automatically — **this step requires a Jira
   administrator** (project admin alone is not enough); non-admins will see a
   message asking a Jira admin to enable it.

## Good to know

- **Company-managed projects only (v1).** Team-managed projects are detected
  automatically and shown a clear "not supported yet" message instead of a
  broken settings page.
- **Enforcement covers creation only (v1).** Changing an existing work item's
  type (type field edit, Move, convert to/from subtask) is not yet covered —
  on the roadmap. Bulk-editing subtasks is intentionally out of scope: Jira
  does this natively.
- **Disabling keeps the validator attached but inert.** The Enabled toggle
  off preserves your matrix and leaves the validator on the workflow in an
  inactive state; to remove it from the workflow entirely, delete it in the
  workflow editor's Validators section.
- **Shared workflows.** If several projects share a workflow, the validator
  appears in each of their workflow editors. Projects that never configured
  Subtask Rules are unaffected — with no rules saved, everything is allowed.

## Permissions

The app reads the project's issue types and workflow configuration, and
stores your rules matrix as a project property **inside your Jira site**.
Enabling/disabling enforcement updates the project's workflow (classic
`manage:jira-configuration` scope). The app runs entirely on Atlassian Forge
with **no egress**: your data never leaves Atlassian's infrastructure.

## Support

Questions or problems: see [Support](../support.html) — portal and email,
response within one business day.

- [Privacy policy](privacy.html)
- [End User License Agreement](eula.html)
