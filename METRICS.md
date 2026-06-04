# Metrics & How We Hit 80% in 24 Hours

---

## The Core Goal, Decoded

> "80% of interviews should get scheduled within 24 hours"

This means: out of ~500 requests received today, at least **400 must have a confirmed Calendly booking by the same time tomorrow.**

The remaining 20% (100 candidates) can be scheduled later - they're either hard-to-reach, have personal reasons, or are in a follow-up cycle.

---

## Why 80% is Achievable (The Math)

Here's why this target is realistic if the process is followed correctly:

| Scenario | % of Candidates | Action | Expected Conversion |
|---|---|---|---|
| **Highly engaged** - sees WA, books immediately | ~35% | W1 → Books on their own | 100% same day |
| **Responsive** - needs one follow-up | ~25% | W1 + W2 or call → books | 100% same day |
| **Delayed** - needs call + evening nudge | ~20% | W3/W4/W5 + call → books | ~90% same day |
| **Hard to reach** - multiple attempts needed | ~15% | Full sequence, may spill to Day 2 | ~50% same day |
| **Unresponsive / Declined** | ~5% | Escalated or closed | ~0% same day |

**Expected same-day rate:** ~35 + 25 + 18 + 7.5 = **~85%**

With a good process, 80% is a minimum, not a stretch.

---

## Daily Checkpoints - Are We On Track?

### By 10:00 AM
- 100% of new requests contacted (W1 + Email sent)
- Sheet fully updated
- **If not:** Ram and Shyam are behind. Identify the bottleneck - are they stuck on one company? Is the sheet slow?

### By 12:30 PM
- ~25% of today's requests already scheduled (the highly engaged group)
- All non-responsive candidates flagged for 2 PM calls
- **Red flag:** If only 10-15% scheduled by noon, the evening will be very hectic

### By 4:00 PM
- ~55-60% of requests scheduled
- All call-batch candidates have been reached or voicemail left
- **Red flag:** If under 50%, both interns should pause and do a rapid sweep of "WA Read No Reply" group - these are the lowest-hanging fruit

### By 6:30 PM (EOD)
- Target: 80%+ scheduled
- Red-flagged candidates (approaching 24 hrs) escalated to senior
- **Red flag:** If under 70%, something systemic went wrong - possibly Calendly links broken for a company, or contact info issues. Senior must be looped in.

---

## Weekly Reporting

At the end of each week, share a summary with the senior:

| Metric | Mon | Tue | Wed | Thu | Fri | Weekly Avg |
|---|---|---|---|---|---|---|
| Total requests | | | | | | |
| Scheduled in 24 hrs | | | | | | |
| % in 24 hrs | | | | | | |
| Escalated | | | | | | |
| Declined | | | | | | |
| Invalid contact | | | | | | |
| Avg hours to schedule | | | | | | |

**Target:** Weekly average ≥ 80% scheduled in 24 hrs.

---

## Root Cause Analysis - When We Miss the Target

If a day comes in under 80%, don't just note it - understand why:

### Reason 1: Volume spike
- **Symptom:** More than 600 requests on a given day
- **Fix:** Senior needs to know by 10 AM so extra help can be arranged

### Reason 2: Calendly issues
- **Symptom:** Multiple candidates report broken links, or a company's slots are full
- **Fix:** Flag every affected company in a dedicated "Blocker" tab in the sheet. Senior resolves with the company.

### Reason 3: Wrong contact info
- **Symptom:** More than 5% of candidates have invalid phone/email
- **Fix:** Request the company to re-verify candidate contact details before sending new requests

### Reason 4: Interns running behind
- **Symptom:** First-touch messages not all sent by 9:30 AM
- **Fix:** Set a strict 9:00-9:30 AM window. Use the batch method - never process one-by-one.

### Reason 5: Candidates are less responsive on certain days
- **Observation (hypothetical):** Monday mornings and Friday afternoons may have lower response rates
- **Fix:** Send evening reminders earlier on Fridays (4:30 PM instead of 5:30 PM). On Mondays, prioritise calls over messages.

---

## Future Improvements (Automation Ideas)

These are things Ram and Shyam can't do now (no tools), but would dramatically improve the system:

| Idea | Impact | Complexity |
|---|---|---|
| WhatsApp Business API integration - auto-send W1 immediately on request receipt | +10-15% same-day rate | Medium |
| Automated reminder at T+2hrs if no booking | Eliminates manual W2 entirely | Medium |
| Calendly webhook to auto-update sheet when booking happens | Eliminates manual status updates | Low |
| SMS automation for candidates without WhatsApp | Covers the 5–10% gap | Low |
| Candidate response tracking dashboard (real-time) | Gives visibility into who's slipping | Medium |
| Smart assignment: route candidates to the intern with fewer open tasks | Balances load dynamically | High |

**Priority for first automation:** Calendly webhook → sheet auto-update. This alone saves 15-20 minutes of sheet-updating time per intern per day, and eliminates human error in status tracking.

---

## The One Number That Matters

At the end of every single day, ask this one question:

> **"What percentage of today's requests got scheduled within 24 hours?"**

Everything else - the templates, the scripts, the edge case guide - exists to make that number ≥ 80%.

If it's above 80%: great, keep doing what you're doing.  
If it's between 70-80%: identify the top 2 reasons and fix them tomorrow.  
If it's below 70%: something is fundamentally broken. Escalate to senior immediately.
