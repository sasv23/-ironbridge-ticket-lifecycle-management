# IT Service Management & Ticket Lifecycle (Jira Service Management)

**Ironbridge Bank & Trust | MRA Finding #3 | Simulated enterprise environment**

---

## Video Walkthrough

**[▶ Watch the 3 to 7 minute walkthrough]([https://www.loom.com/share/f7e45e300c1c4133b0f8c1411bfc7293])**

---

## Problem Statement

Ironbridge Bank & Trust had no way to receive, track, prioritize or escalate IT work. Requests arrived through drive-by desk visits, text messages at 9 PM, and an email chain 52 replies deep containing four unrelated problems.

The failure that mattered most: the head teller at the Elm Street branch reported that the check scanner's batch upload was failing intermittently. She reported it three weeks before I arrived. Nobody answered, so she had been driving deposits to another branch every afternoon since.

Nothing was tracked, nothing had an owner, and when the examiners asked for evidence of an incident management process there was nothing to show them. Sticky notes are not evidence.

What struck me most about that email chain was that there was no way to determine where any of the problems originated, whether they were still broken, fixed, or the initial report date. Without a clear timestamp, nothing could be organized and prioritized.

---

## Solution Overview

I deployed Jira Service Management as the single intake channel for the bank.

I configured request types across all four work categories (incident, service request, change and problem), each written in language a teller can navigate rather than IT language. I built a priority matrix defining impact and urgency in banking terms, then configured SLA schemes with separate response and resolution goals per priority, business hour calendars, and pause conditions.

I built queues so a technician always knows what to work next, including an Unassigned queue that makes ownerless work visible.

I then worked a realistic bank queue end to end, including a full functional escalation and an intermittent failure that I converted from a repeat incident into a tracked problem.

---

## Key Work

**Built one front door.** Replaced untracked intake with a portal and defined request types, so nothing arrives without being recorded.

**Made priority a calculation, not an opinion.** Priority comes from impact combined with urgency, documented in a matrix with worked banking examples. Seniority is not urgency.

**Put a clock on the promise.** Configured response and resolution SLAs per priority, with calendars reflecting when a given system actually matters and pause conditions for tickets genuinely waiting on the customer.

**Separated the incident from the problem.** The check scanner had been restarted repeatedly and closed each time. I resolved it with a workaround, labelled it a workaround in the ticket, and opened a linked problem ticket for the underlying cause.

**Escalated with a package, not a shrug.** The full escalation note is in `escalation-note.md`. It states the issue, the impact, what I tried and what happened, what I ruled out, and what I needed from the vendor.

**Produced examiner evidence.** SLA performance and created versus resolved reporting, which is the demonstration of timely resolution the finding asked for.

---

## Tools Used

Jira Service Management (ServiceNow is the enterprise equivalent).

---

## Repository Contents

- `priority-matrix.md` - impact and urgency definitions in banking terms, with worked examples
- `sla-definitions.md` - response and resolution goals per priority and the reasoning behind each calendar
- `escalation-note.md` - the full escalation I wrote for the scanner
- `evidence/` - exported SLA performance and created versus resolved reports
- `screenshots/` - visual evidence across the ticket lifecycle

---

## What I Learned

**The update is the service.**
Users tolerate a problem taking time. What they cannot tolerate is silence, which is why a ticket worked hard for three days with no updates produces the same anger as one nobody touched, and this is exactly what happened to the head teller. She waited three weeks with no reply, so she stopped waiting and took matters into her own hands. She started driving to another branch about 9 miles away every day to keep deposits getting processed. One short message saying someone had her ticket might have kept her from making those drives.

**A workaround is not a fix.**
Restarting the scanner restored service, but nothing about the cause changed, so the same failure would eventually come back. If I had closed it as resolved and moved on, the problem would have disappeared from view, and the next teller would hit it with nobody tracking it. That is why I opened a problem ticket and left it open until it has been fixed by the vendor.

**The fourth identical ticket is not an incident.**
Incidents are events and a problem is a pattern, which means that once the pattern has been noticed, it then becomes the service desk's job. Noticing turns a repeated incident into a problem ticket with an owner, so the cause gets fixed for good.

**The tool doesn't always match the checklist.**
When I tried to resolve my first ticket, the Resolution dropdown was empty and I couldn’t close anything. I had to find the Resolutions list in Jira’s admin settings and add Done myself. It taught me to check the settings behind a feature when it doesn’t work, not just retry the feature.

---

*Built as part of the TotalThreat IT & IAM Career Accelerator. Ironbridge Bank & Trust is a simulated enterprise environment and not a real employer. The service desk configuration, documentation and ticket handling in this repository are my own work.*

