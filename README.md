# Weekday Scheduling Assignment — Submission

**Submitted by:** [Your Name]  
**Date:** June 4, 2026  
**Assignment:** Build a scheduling system as strong as Zomato's — a ToDo playbook for interns Ram and Shyam to schedule 500+ interviews/day via Calendly, with 80% done within 24 hours.

---

## Table of Contents

1. [Problem Breakdown & Assumptions](#1-problem-breakdown--assumptions)
2. [Thought Process & Design Decisions](#2-thought-process--design-decisions)
3. [Work Division: Ram vs Shyam](#3-work-division-ram-vs-shyam)
4. [The Master SOP — Daily Playbook](./SOP.md)
5. [Communication Templates](./templates/)
6. [Tracking Sheet Structure](./tracking/TRACKING_SHEET.md)
7. [Edge Case Handling Guide](./EDGE_CASES.md)
8. [Metrics & How We Hit 80% in 24 hrs](./METRICS.md)

---

## 1. Problem Breakdown & Assumptions

### What we're actually solving

Every day, 100 companies send 500+ Calendly links expecting us to get their candidates to book. The candidates have already said yes to the interview. The ONLY job is to get them to click the link and pick a slot. That sounds simple. It isn't — because people are unpredictable.

The real problem is not logistics. It's **human behaviour under low urgency**. The candidate agreed days ago, has probably forgotten, and now has zero incentive to act immediately. Our job is to create that urgency without being annoying.

### Breaking the number down

| Metric | Number |
|---|---|
| Companies per day | 100 |
| Total requests per day | ~500 |
| Requests per company (avg) | 5 |
| Requests per intern per day | ~250 |
| Requests per intern per hour (8hr day) | ~31 |
| Target: scheduled within 24 hrs | 400 (80%) |
| Acceptable backlog (max 20%) | 100 |

### Assumptions Made

1. **Candidates are in India (IST)** — WhatsApp is the highest-engagement channel, followed by phone, then email.
2. **Working hours are 9 AM – 7 PM IST** — 10-hour window. Evening follow-ups matter because candidates are more responsive after 5 PM.
3. **Each "request" = one candidate + one Calendly link from one company** — Companies provide the link; we provide it to the candidate.
4. **Candidates have a mobile number and email on file** — Weekday already has this from the initial application.
5. **"Scheduled within 24 hrs" = the slot is booked on Calendly** — Not that the interview happened, just that it's on the calendar.
6. **Ram and Shyam have phones with WhatsApp** and can make calls.
7. **There is a shared Google Sheet** (master tracker) that both Ram and Shyam update in real time.
8. **Companies are OK with slots being booked up to 5 days out** — "Scheduling within 24 hrs" refers to the booking action, not the interview date.
9. **A candidate who doesn't schedule within 48 hrs is escalated** to a senior on the team — Ram and Shyam don't chase indefinitely.
10. **No automated tool exists yet** — This is a manual process. Future automation is noted in Metrics.

---

## 2. Thought Process & Design Decisions

### Why WhatsApp First (Not Email)

In India, email open rates hover around 20–25%. WhatsApp open rates are 90%+. If we lead with email, we lose 75% of candidates in the first touch. WhatsApp also shows "read" receipts — we know within minutes if someone saw our message.

**Decision:** First outreach is always WhatsApp + Email simultaneously. Phone call only if no WhatsApp response in 2 hours.

### Why Company-Based Split (Not Time-Based)

Two options were considered:
- **Option A:** Ram handles morning requests, Shyam handles afternoon
- **Option B:** Ram handles Companies 1–50, Shyam handles Companies 51–100

Option A creates a handoff problem. If a candidate first contacted by Ram at 10 AM doesn't respond until 4 PM, does Shyam now own it? Confusion = dropped candidates.

**Option B wins:** Ownership is clear. Ram owns all candidates from his 50 companies, forever, until scheduled or escalated. No handoffs, no confusion. College interns thrive on clarity.

### Why a Timed Sequence Matters

Without a defined follow-up schedule, interns either:
- Follow up too aggressively (spamming candidates = bad for Weekday's brand)
- Follow up too loosely (candidates forget again)

**Decision:** Fixed sequence — T+0 (first contact), T+2hrs (if unread on WhatsApp), T+4hrs (call), T+24hrs (second round). Interns follow this like a clock. No improvisation needed.

### The "Soft Deadline" Technique

Candidates respond faster when they believe slots are running out. Every message includes a subtle urgency signal:

> "The company has limited slots this week — the link expires in 24 hours if not booked."

This is truthful (Calendly slots DO fill up) and effective without being dishonest.

### Batch Processing Over Continuous Processing

Processing one request at a time is inefficient. Instead:
- **9:00–9:30 AM** — Batch-pull all new requests, send all first-touch messages in one go
- **11:30 AM** — Follow-up batch for anyone who didn't respond to 9 AM outreach
- **2:00 PM** — Call batch for anyone still unresponsive
- **5:30 PM** — Evening reminder batch (people check phones after work)

This "wave" approach means interns aren't context-switching every few minutes.

---

## 3. Work Division: Ram vs Shyam

### Split Strategy

| | Ram | Shyam |
|---|---|---|
| **Companies owned** | Companies 1–50 (A–M alphabetically) | Companies 51–100 (N–Z alphabetically) |
| **Candidates/day** | ~250 | ~250 |
| **Primary channel** | WhatsApp + Email | WhatsApp + Email |
| **Escalation calls** | Calls for his own candidates | Calls for his own candidates |
| **Backup role** | Covers Shyam's calls if Shyam is unavailable | Covers Ram's calls if Ram is unavailable |
| **Sheet columns** | Columns A–H | Columns I–P (or separate tab) |

### Daily Sync

- **9:00 AM** — Both interns open the master sheet, claim the day's new requests
- **1:00 PM** — 5-minute standup: who's stuck, any blockers?
- **6:00 PM** — EOD update: mark all statuses, flag anyone hitting the 24hr deadline

### Escalation to Senior

If any candidate reaches **T+36 hours** with no booking, Ram/Shyam flags them in the sheet (red highlight) and messages the senior on duty. They don't keep chasing — that's not their job.

---

## Files in This Submission

| File | What it contains |
|---|---|
| `SOP.md` | The actual step-by-step daily playbook Ram and Shyam follow |
| `EDGE_CASES.md` | Every weird situation and exactly what to do |
| `METRICS.md` | How to measure the 80% goal and course-correct |
| `templates/whatsapp_templates.md` | Ready-to-send WhatsApp messages |
| `templates/email_templates.md` | Ready-to-send email templates |
| `templates/call_scripts.md` | Word-for-word call scripts |
| `tracking/TRACKING_SHEET.md` | Google Sheet structure + column definitions |
