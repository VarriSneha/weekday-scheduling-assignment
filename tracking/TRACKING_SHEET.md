# Tracking Sheet Structure

> This document defines the Google Sheet structure that Ram and Shyam use to track all 500+ daily requests. Make a copy of this sheet every day  one sheet per day.

---

## Sheet Name Format

`Scheduling_Tracker_YYYY-MM-DD`  
Example: `Scheduling_Tracker_2026-06-04`

---

## Columns (in order)

| # | Column Name | Data Type | Who fills it | Example |
|---|---|---|---|---|
| A | **Request ID** | Auto-number | Auto (or senior) | WD-2026-0001 |
| B | **Date Received** | Date | Auto | 04-Jun-2026 |
| C | **Assigned To** | Text | Ram / Shyam | Ram |
| D | **Company Name** | Text | Auto (from request) | Acme Corp |
| E | **Role** | Text | Auto | Software Engineer |
| F | **Candidate Name** | Text | Auto | Priya Sharma |
| G | **Candidate Phone** | Phone | Auto | 9876543210 |
| H | **Candidate Email** | Email | Auto | priya@gmail.com |
| I | **Calendly Link** | URL | Auto (from company) | calendly.com/acme/priya |
| J | **Status** | Dropdown | Ram / Shyam | WA Sent |
| K | **WA Sent Time** | Time | Ram / Shyam | 9:12 AM |
| L | **WA Read?** | Yes/No | Ram / Shyam | Yes |
| M | **Email Sent Time** | Time | Ram / Shyam | 9:15 AM |
| N | **Call Attempted?** | Yes/No | Ram / Shyam | Yes |
| O | **Call Time** | Time | Ram / Shyam | 2:05 PM |
| P | **Call Outcome** | Dropdown | Ram / Shyam | Will Book |
| Q | **Scheduled?** | Yes/No | Ram / Shyam | No |
| R | **Scheduled Time** | DateTime | Ram / Shyam | 05-Jun 3:00 PM |
| S | **Hours to Schedule** | Auto-calc | Formula | 6.5 |
| T | **Notes** | Free text | Ram / Shyam | "Says will book after 5 PM" |
| U | **Escalated?** | Yes/No | Ram / Shyam | No |
| V | **Escalation Reason** | Text | Ram / Shyam | No slots on Calendly |
| W | **Final Status** | Dropdown | Ram / Shyam | Scheduled |

---

## Status Dropdown Values (Column J)

These are the only accepted values. Do not type freehand  use the dropdown.

| Status | Meaning |
|---|---|
| `New` | Request just assigned, not contacted yet |
| `WA Sent` | First WhatsApp sent |
| `WA Follow-up 1` | Second WhatsApp sent |
| `WA Read No Reply` | WhatsApp opened but no reply |
| `SMS Sent` | SMS sent (no WhatsApp) |
| `Email Sent` | Email sent |
| `Call - Will Book` | Spoke on call, candidate said they'll book |
| `Call - Reschedule` | Candidate wants a different time |
| `Call - No Answer` | Called, no pickup |
| `Call - Declined` | Candidate declined the interview on the call |
| `Voicemail Left` | Voicemail message left |
| `Scheduled` | Calendly slot booked ✅ |
| `Cancelled - Re-outreach` | Candidate booked and then cancelled |
| `Stalled` | No response after full sequence, still trying |
| `Escalated` | Handed off to senior |
| `Declined - Not Interested` | Candidate explicitly said no |
| `Declined - Got Other Offer` | Candidate accepted another offer |
| `Invalid Contact Info` | Phone/email doesn't work |
| `Do Not Contact` | Candidate asked to stop |
| `On Hold - Personal` | Candidate has personal situation, follow up later |
| `Waiting - No Slots` | Calendly has no available slots |

---

## Final Status Dropdown Values (Column W)

| Final Status | Meaning |
|---|---|
| `Scheduled` | Successfully booked ✅ |
| `Declined` | Candidate said no |
| `Escalated` | Senior took over |
| `Unresponsive` | No response after 48 hrs |
| `Invalid` | Bad contact info, couldn't reach |
| `On Hold` | Paused, follow up at a later date |
| `Cancelled` | Booked and cancelled, no re-booking |

---

## Key Formulas

### Hours to Schedule (Column S)
```
=IF(Q2="Yes", (R2 - B2) * 24, "")
```
Calculates hours between when the request was received and when it was scheduled.

### Is 24-Hour Risk? (add a conditional formatting rule)
Color row RED if:
```
=AND(Q2="No", (NOW() - B2) * 24 > 20)
```
This flags any unscheduled candidate who is within 4 hours of the 24-hour deadline.

### Daily Scheduled Count (for summary tab)
```
=COUNTIF(W:W, "Scheduled")
```

### 24-Hour Success Rate
```
=COUNTIFS(W:W, "Scheduled", S:S, "<="&24) / COUNTA(A:A) * 100
```

---

## Sheet Tabs

| Tab Name | Purpose |
|---|---|
| `Daily_[Date]` | Main tracker for that day's requests |
| `Summary` | Auto-updated dashboard showing KPIs |
| `Master_All` | Running log of all requests ever (don't edit directly) |
| `Companies` | List of all 100 companies with their Calendly base URLs |
| `Templates` | Quick reference for message templates |

---

## Summary Tab - KPIs to Track Daily

| Metric | Target | Formula |
|---|---|---|
| Total requests today | ~500 | `=COUNTA(Daily!A:A) - 1` |
| Scheduled today | — | `=COUNTIF(Daily!W:W,"Scheduled")` |
| % Scheduled in 24 hrs | ≥ 80% | `=COUNTIFS(Daily!W:W,"Scheduled",Daily!S:S,"<="&24)/COUNTA(Daily!A:A)*100` |
| Pending (still in flight) | — | `=COUNTIF(Daily!J:J,"<>Scheduled")` |
| Declined | — | `=COUNTIFS(Daily!W:W,"Declined*")` |
| Escalated | — | `=COUNTIF(Daily!U:U,"Yes")` |
| Ram's scheduled | — | `=COUNTIFS(Daily!C:C,"Ram",Daily!W:W,"Scheduled")` |
| Shyam's scheduled | — | `=COUNTIFS(Daily!C:C,"Shyam",Daily!W:W,"Scheduled")` |

---

## Sheet Hygiene Rules

1. **Update within 5 minutes of every action** - stale data breaks the system
2. **Never delete rows** - mark as invalid instead
3. **Never change a colleague's rows without telling them**
4. **Freeze rows 1 and 2** (header + filter row)
5. **Sort by "Date Received" ascending** at start of day
6. **Archive previous day's sheet** at 9 AM before starting the new day
