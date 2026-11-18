---
kind: doc
status: published
title: Scheduled maintenance announcements
feature: Scheduled maintenance announcements
jira_issue: SCRUM-5
published_at: '2026-11-18T10:38:02.207Z'
---
# Scheduled maintenance announcements

## Overview
Scheduled maintenance announcements let you tell status-page subscribers about planned work before it starts, instead of leaving them to discover it when components degrade. You create the announcement in the admin console, pick the affected components and time window, and optionally email subscribers. Between the start and end times, a maintenance banner appears on your public status page and affected components show a wrench icon.

## Prerequisites
- Workspace admin access to the Beacon admin console.
- Components already defined in your workspace, so they appear in the **Affected components** list.

## Steps
1. In the admin console, go to **Announcements › New maintenance**.
2. Enter a **Title** (required, maximum 120 characters) — for example, "Database maintenance — EU region".
3. Set the **Start** date and time of the maintenance window. It is interpreted in the timezone you select in step 5.
4. Set the **End** date and time, also in the timezone you select in step 5. The end must be after the start.
5. Check the **Timezone** selector. It defaults to your workspace timezone; change it if the window is defined in another zone.
6. Choose a **Severity** from the dropdown (Minor, Major, or Critical).
7. Under **Affected components**, tick each component the maintenance will affect. At least one is required.
8. Optionally, add a **Description** explaining the work.
9. Leave **Notify subscribers** on to email subscribers when you publish and send a reminder 1 hour before the start time, measured in the announcement's selected timezone, or switch it off to publish silently.
10. Select **Publish** to make the announcement live, or **Save as draft** to finish it later. Select **Cancel** to discard the form without saving.
11. To call off published maintenance, edit or cancel the announcement any time up to the end time. **Warning:** cancelling a published announcement emails subscribers if the start notification has already been sent.

## FAQ

**What do subscribers and visitors actually see?**
Subscribers receive an email on publish and a reminder 1 hour before the start time, in the announcement's selected timezone, if **Notify subscribers** is on. Between the start and end times, the public status page shows an amber maintenance banner above the component list with the title and the time window converted to the visitor's local timezone, and each affected component shows a wrench icon instead of its status dot.

**Can I change or call off an announcement after publishing?**
Yes. Announcements can be edited or cancelled any time up to the end time. Cancelling notifies subscribers only if the start notification had already been sent.

**Why can't I publish?**
Publishing requires a title, a start time, an end time, and at least one affected component, and the end must be after the start.

**Can I set up a repeating maintenance window or send SMS alerts?**
No. Recurring maintenance windows are not supported, and v1 sends email notifications only — no SMS or webhooks.
