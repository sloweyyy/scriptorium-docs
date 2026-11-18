---
kind: doc
status: published
title: Status page subscriber management
feature: Status page subscriber management
jira_issue: SCRUM-6
published_at: '2026-11-18T10:48:46.637Z'
---
# Status page subscriber management

## Overview
Subscriber management gives workspace admins a single screen to audit, invite, and remove status page subscribers. You can see every subscriber's email, followed components, delivery mode, and subscribed date, and export that list as CSV for audits. You can also set a workspace-wide digest send time so subscribers who don't need every update get one daily summary instead.

## Prerequisites
- Workspace admin access (the subscriber list and CSV export are available to workspace admins only).
- Email addresses for anyone you plan to invite — up to 50 per invite.

## Steps

1. In the admin console, open **Subscribers → Manage** to load the subscriber table. Each row shows the subscriber's email, the components they follow, their delivery mode, and the date they subscribed.
2. Use the search box above the table to find a specific subscriber, or use the bulk-select column to act on several rows at once.
3. To add subscribers, select **Invite subscribers** (the primary action) and enter up to 50 email addresses at once. ⚠️ Each address receives a confirmation email as soon as you send the invite. Invited addresses become subscribers only after they confirm.
4. To change how often a subscriber hears from you, use the two-option segmented control in their row: **Immediate** sends an email per status change; **Daily digest** sends one email covering the previous 24 hours. Immediate is the default.
5. To set when the digest goes out, choose the workspace **digest send time** — an hour of the day plus a timezone selector. The timezone defaults to the workspace timezone; whichever timezone you select is the one the digest hour is evaluated in, so confirm it before saving. On days with no status changes, the digest is skipped entirely.
6. To remove a subscriber, select their row and choose **Remove**. ⚠️ Removal is immediate and cannot be undone from this screen; the subscriber receives no notification that they were removed.
7. To take the list elsewhere, select **Export CSV** (the secondary action). The export contains email, components, delivery mode, and subscribed date.

## FAQ

**Can I set a different delivery mode for each component a subscriber follows?**
No. A subscriber's delivery mode applies to everything they follow. Per-component delivery modes are out of scope for this version.

**What happens if a subscriber changes their own settings?**
Subscribers can change their delivery mode or unsubscribe using the footer link in any status email. Those changes appear in the admin list within a minute.

**Can I import a list of subscribers from a CSV file?**
No. CSV import is out of scope for v1 — adding subscribers is invite-only, up to 50 email addresses at a time. CSV export is supported.

**Will subscribers get an empty digest on quiet days?**
No. The daily digest is skipped entirely on days with no status changes.
