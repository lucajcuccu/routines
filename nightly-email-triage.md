# nightly-email-triage

Schedule: every morning at 3:30 AM Pacific (cron: `30 7 * * *`).
Connectors required: Gmail, Google Calendar.

## Prompt

Triage lucajcuccu@gmail.com's Gmail inbox from the last 24 hours. Use the Gmail and Google Calendar tools.

**STEP 1 — GATHER:** Search Gmail with query `in:inbox newer_than:1d` and list matching threads. Skip any thread that already has a label starting with "Triage" (Triage/Action Needed, Triage/Reply Needed, or Triage/FYI). Read each remaining thread's content to classify it.

**STEP 2 — LABEL:** Look up the existing Gmail labels and apply EXACTLY ONE of these existing labels to each remaining thread (do not create new labels):

- **"Triage/Action Needed"** — deadlines, bills or payments due, account/domain verification requirements, security issues, travel changes or cancellations, anything with real consequences if ignored.
- **"Triage/Reply Needed"** — personal or business emails from real humans waiting on a response from me.
- **"Triage/FYI"** — legitimate informational mail: receipts for meaningful purchases, statements, travel confirmations, school announcements, shipping notices.
- **NO LABEL** — marketing, promotions, newsletters, social media notifications, price alerts. Leave these completely untouched.

**STEP 3 — CALENDAR:** For any email containing a concrete date, deadline, or appointment that affects me, create an event on the PRIMARY Google Calendar in timezone America/Los_Angeles:

- Bills/loan payments: all-day event on the due date, with the amount in the title (e.g. "Chase mortgage payment due — $2,450").
- Hard deadlines: all-day event titled "DEADLINE: ...".
- Appointments, reservations, meetings: timed events at the stated time.

Before creating each event, list the calendar events on that date and SKIP creating it if a matching event already exists — including Gmail's auto-created flight/reservation events. Put the source email (sender + email date) in the event description. NEVER create events for promotional expirations, sale end dates, or offer deadlines.

**STEP 4 — SUMMARY:** End with a short summary containing: counts per label; each Action Needed and Reply Needed item as sender, subject, and one-line reason; and any calendar events created (or "none").

**HARD CONSTRAINTS:** Never delete, archive, mark-as-read, or send any email. Never modify or delete existing calendar events. The only mutations allowed are adding Gmail labels and creating new calendar events. If Gmail or Calendar tools are unavailable, report that in the summary instead of attempting workarounds.
