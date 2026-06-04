# The Master Playbook — Daily SOP for Ram & Shyam

> **How to use this doc:** Follow it exactly, in order, every day. Don't improvise. If something isn't covered here, check EDGE_CASES.md. If it's not there either, flag it to your senior.

---

## Before You Start — One-Time Setup (Day 1 only)

- [ ] Save all WhatsApp templates to your phone's "Saved Messages" so you can copy-paste fast
- [ ] Bookmark the master tracking sheet
- [ ] Save the call script PDF on your phone
- [ ] Set three daily alarms: **9:00 AM**, **11:30 AM**, **2:00 PM**, **5:30 PM**
- [ ] Set up WhatsApp Business (if not already) — enables quick reply templates
- [ ] Confirm with your senior: which 50 companies are yours?

---

## Daily Schedule — The Clock

| Time | What you do |
|---|---|
| **9:00 AM** | Morning batch: pull new requests, send first-touch messages |
| **9:30 AM** | Sheet updated, all new candidates contacted |
| **11:30 AM** | Follow-up batch: anyone who didn't open WhatsApp |
| **12:00 PM** | Sheet updated |
| **1:00 PM** | Sync with your partner (5 min) |
| **2:00 PM** | Call batch: anyone with no response to any channel |
| **3:30 PM** | Sheet updated |
| **5:30 PM** | Evening reminder batch: warm message to anyone pending |
| **6:30 PM** | EOD: close out day, flag 24hr-risk candidates, prep for tomorrow |

---

## Step 1 — Morning Batch (9:00–9:30 AM)

### 1.1 Pull today's requests

1. Open the master Google Sheet
2. Filter by: **"Date Received" = today** AND **"Assigned To" = your name** AND **"Status" = "New"**
3. You should see your list for today (~250 rows)
4. If any rows are blank in "Assigned To", claim them now (type your name)

### 1.2 Send first-touch messages (do this for EVERY new request)

For each candidate in your list, do ALL THREE of the following **at the same time**:

**Step A — WhatsApp message** (takes ~10 seconds per candidate)
- Open WhatsApp → search candidate's number
- Send **Template W1** (see `templates/whatsapp_templates.md`)
- Note: paste the company name and Calendly link from the sheet into the template
- Update sheet: **"WA Sent Time"** = now, **"Status"** = "WA Sent"

**Step B — Email** (can be done in bulk via Gmail)
- Use **Template E1** (see `templates/email_templates.md`)
- CC: nobody (keep it personal)
- Update sheet: **"Email Sent Time"** = now

**Efficiency tip:** Open 10 WhatsApp chats in browser tabs, fill in the template for each, then send all 10. Then do 10 emails. Batch of 10 takes about 8–10 minutes. In 30 minutes you can process ~250 candidates.

### 1.3 Mark your sheet

After every candidate is contacted, their row should show:
- Status: `WA Sent`
- WA Sent Time: `9:15 AM` (or whenever you sent it)
- Email Sent Time: `9:20 AM`

---

## Step 2 — Follow-Up Batch (11:30 AM)

### Who needs a follow-up?

Filter sheet: **"Status" = "WA Sent"** AND **"WA Read?" = "No"** AND WA was sent more than 2 hours ago.

These people never opened your WhatsApp. Try a different approach.

### What to do

**Option A — WhatsApp read receipt says "delivered but not read" (two grey ticks)**
- Send **Template W2** — a softer nudge, slightly different wording
- Update sheet: Status → `WA Follow-up 1`

**Option B — WhatsApp not delivered (one grey tick, or phone off)**
- Try SMS: same message, plain text. Not everyone has WhatsApp
- Update sheet: Status → `SMS Sent`

**Option C — WhatsApp read receipt says "read" (two blue ticks) but no reply**
- This person saw it and chose not to act. Send **Template W3** — urgency message
- Update sheet: Status → `WA Read No Reply`

---

## Step 3 — Call Batch (2:00 PM)

### Who gets a call?

Filter: **Status** is `WA Follow-up 1` or `SMS Sent` or `WA Read No Reply` AND last contact was before 12:30 PM.

These are people who haven't responded to any written message. A phone call almost always gets a response.

### How to make the call

1. Use **Call Script CS1** (see `templates/call_scripts.md`)
2. The call should take 60–90 seconds max
3. Three outcomes — update sheet accordingly:

| Outcome | Status to set | Next action |
|---|---|---|
| Candidate picks up and agrees to book | `Call - Will Book` | Follow up in 1 hour to confirm booking |
| Candidate picks up and gives a reason (busy, traveling, etc.) | `Call - Reschedule` | Note their preferred time in "Notes" column, follow up at that time |
| Candidate doesn't pick up | `Call - No Answer` | Leave voicemail (Script VM1), try again at 5:30 PM |
| Candidate picks up but declines the interview | `Call - Declined` | Immediately notify senior — this is unusual and needs to be escalated |

### If call goes to voicemail

Leave **Voicemail Script VM1** — it's short (20 seconds). Then also send **Template W4** on WhatsApp right after.

---

## Step 4 — Evening Reminder Batch (5:30 PM)

### Who gets an evening message?

Filter: Status is **anything except** `Scheduled`, `Declined`, `Escalated`

Everyone still pending gets a warm evening nudge. People check their phones after work. This is often the most effective touch.

### What to send

- Use **Template W5** — it's casual and friendly, not corporate
- This is the last message for the day. Do NOT send more than 2 WhatsApp messages + 1 call in a single day per candidate. More than that feels like spam.

---

## Step 5 — EOD Wrap-Up (6:30 PM)

### What to do

1. Sort sheet by "Time Since First Contact" (oldest first)
2. Any candidate with **>20 hours elapsed and Status ≠ Scheduled** → highlight row RED
3. Send a quick message to your senior: "Hi [Name], flagging 5 candidates approaching the 24hr mark: [paste names]. Any advice?"
4. For red-flagged candidates, send **Template W5** one more time if you haven't sent an evening message yet
5. Update "EOD Notes" column for each stuck candidate — what happened, what you tried

### Count your numbers

At EOD, check:
- How many scheduled today? (Target: 80% of your day's requests)
- How many still pending?
- How many escalated?

Share this with your partner and senior in the group chat.

---

## Special Situations — Quick Reference

| Situation | What to do |
|---|---|
| Candidate scheduled on their own (no action needed) | Update status to `Scheduled - Self`, log time |
| Company sends an updated Calendly link | Update the link in the sheet, re-send to all pending candidates for that company |
| Candidate asks to reschedule after booking | Note in sheet, send new link from company |
| Company's Calendly has no available slots | Flag to senior immediately — this blocks ALL that company's candidates |
| Two candidates fight over the same slot | Whoever booked first wins — let the other know and re-send the link |
| Candidate is rude or abusive on call | End call politely, update sheet as `Declined`, escalate to senior |

For detailed edge cases, see **EDGE_CASES.md**.

---

## The Non-Negotiables (Never Break These Rules)

1. **Never book a slot without the candidate's explicit confirmation** — don't click "book" for them
2. **Never contact a candidate more than 3 times in one day** (WA + Email + Call = that's already 3)
3. **Always update the sheet within 5 minutes of any action** — stale data breaks the whole system
4. **Never promise a specific interview time to a candidate** — the company decides based on Calendly
5. **Always be polite, even if the candidate is not** — you represent Weekday's brand
6. **If you're unsure, ask your senior.** Don't guess.
