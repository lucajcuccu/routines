# nightly-email-triage (v2)

Schedule: every morning at 3:30 AM Pacific (cron: `30 7 * * *`).
Connectors required: Gmail, Google Calendar.

## How to use it (your SOP)

The routine sorts; you decide. Your entire job each morning takes ~5 minutes:

1. **Open your inbox.** Everything important carries one of three labels:
   - **Triage/Action Needed** — has real consequences (bills, deadlines, security). Do the thing, or check that a calendar event was created for it.
   - **Triage/Reply Needed** — a human is waiting on you. A **ready-made draft reply is already in your Drafts folder** — open it, edit, hit send (or discard it).
   - **Triage/FYI** — read if curious, otherwise ignore.
2. **When you're done with something and want it gone:** apply the label **Triage/Done** (in Gmail: open the email → label icon → Triage/Done). That's your "dismiss" button. The next nightly run archives it out of your inbox — not deleted, always findable in All Mail or by searching `label:triage-done`.
   - Shortcut: if you don't care about the paper trail, just press `e` (archive) in Gmail yourself — same result, instantly.
3. **Marketing/promotions never reach you** — the routine archives them automatically overnight.

That's it. Inbox = things awaiting a decision. Everything else is filed, not lost.

## Prompt

Triage lucajcuccu@gmail.com's Gmail inbox. Use the Gmail and Google Calendar tools.

**STEP 0 — SWEEP DONE ITEMS:** Search `in:inbox label:triage-done`. For each result, archive it (remove the INBOX label) and remove its Triage/Action Needed, Triage/Reply Needed, or Triage/FYI label if present. Keep the Triage/Done label as the record.

**STEP 1 — GATHER:** Search Gmail with query `in:inbox newer_than:1d` and list matching threads. Skip any thread that already has a label starting with "Triage". Read each remaining thread's content to classify it.

**STEP 2 — LABEL & CLEAN:** Look up the existing Gmail labels and apply EXACTLY ONE of these existing labels to each remaining thread (do not create new labels):

- **"Triage/Action Needed"** — deadlines, bills or payments due, account/domain verification requirements, security issues, travel changes or cancellations, anything with real consequences if ignored.
- **"Triage/Reply Needed"** — personal or business emails from real humans waiting on a response from me.
- **"Triage/FYI"** — legitimate informational mail: receipts for meaningful purchases, statements, travel confirmations, school announcements, shipping notices.
- **NO LABEL + ARCHIVE** — marketing, promotions, newsletters, social media notifications, price alerts: archive these (remove INBOX label) so the inbox stays clean. When in ANY doubt whether something is promotional versus legitimate, leave it in the inbox untouched — never archive anything that could be personal, financial, or consequential.

**STEP 3 — DRAFT REPLIES:** For each thread labeled "Triage/Reply Needed", create a draft reply on that thread (never send). Match my tone: brief, warm, plain language. Answer what was asked if the answer is knowable from the thread; where information only I have is required, leave an explicit placeholder like [YOUR ANSWER HERE]. Skip creating a draft if one already exists on the thread.

**STEP 4 — CALENDAR:** For any email containing a concrete date, deadline, or appointment that affects me, create an event on the PRIMARY Google Calendar in timezone America/Los_Angeles:

- Bills/loan payments: all-day event on the due date, with the amount in the title (e.g. "Chase mortgage payment due — $2,450").
- Hard deadlines: all-day event titled "DEADLINE: ...".
- Appointments, reservations, meetings: timed events at the stated time.

Before creating each event, list the calendar events on that date and SKIP creating it if a matching event already exists — including Gmail's auto-created flight/reservation events. Put the source email (sender + email date) in the event description. NEVER create events for promotional expirations, sale end dates, or offer deadlines.

**STEP 5 — SUMMARY:** End with a short summary containing: counts per label; number of promos archived and Done items swept; each Action Needed and Reply Needed item as sender, subject, and one-line reason; drafts created; and any calendar events created (or "none").

**HARD CONSTRAINTS:** Never delete anything, never mark-as-read, and NEVER SEND any email — drafts only. Never modify or delete existing calendar events. Archiving (removing the INBOX label) is allowed ONLY in Step 0 (user-labeled Triage/Done) and Step 2 (clearly promotional mail). If Gmail or Calendar tools are unavailable, report that in the summary instead of attempting workarounds.

## One-time setup

Create the label **Triage/Done** in Gmail (the other three Triage labels already exist). Then paste the Prompt section above into the routine's configuration in the Claude app — this file is documentation; the app config is what actually runs.
