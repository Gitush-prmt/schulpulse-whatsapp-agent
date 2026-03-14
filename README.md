# SchulPulse — WhatsApp Parent Communication Agent

## Problem
Parent-teacher communication in Kenyan schools suffers from significant gaps — exacerbated by parents' limited understanding of the Competency-Based Curriculum (CBC), manual messaging overload, missed announcements, and inaccessible updates — leading to low parent engagement, student indiscipline, and declining academic achievements. School admins also waste numerous hours on calls and chases, while parents struggle with shift conflicts, data issues, and school operational changes.

## Solution
SchulPulse, an AI-powered WhatsApp bot, addresses this by enabling 24/7 automated pushes of announcements, schedules, report cards, alerts, and FAQ answers — streamlining communication between parents and teachers/school administrators

## System Architecture
[Screenshot of Make scenario with annotations]

## Tech Stack

| Tool | Role | Why Chosen |
| :--- | :---: | ---: |
| Notion | Row 1 Col 2 | Row 1 Col 3 |
| Claude AI | Row 2 Col 2 | Row 2 Col 3 |
| Make.com | Row 3 Col 2 | Row 3 Col 3 |
| ManyChat | Row 2 Col 2 | Row 2 Col 3 |
| Github | Row 1 Col 2 | Row 1 Col 3 |
| Google Sheets | Row 2 Col 2 | Row 2 Col 3 |
| WhatsApp | Row 1 Col 2 | Row 1 Col 3 |
| Google AI Studio | Row 2 Col 2 | Row 2 Col 3 |
| Google Forms | Row 1 Col 2 | Row 1 Col 3 |
| Framer | Row 2 Col 2 | Row 2 Col 3 |

## Conversation Flow
https://www.figma.com/board/HAWKgfdgwQGztiYspl4cIy/SchulPulse-%E2%80%94-Conversation-Architecture-v1?node-id=0-1&t=EZqICAd870HYWRqs-1
<img width="1787" height="875" alt="Conversation Flow" src="https://github.com/user-attachments/assets/8fedca3a-d056-4d26-beae-f1b918f2e556" />


## WhatsApp Templates
[List all 8 templates with category and use case]

## Key Decisions & Trade-offs
[3–5 bullet decisions with rationale — this is the PM gold]

## Metrics (Pilot Results)
[KPIs with numbers]

## What I Learned
[3 honest lessons]

## Next Phase
[Phase 2 roadmap]
```

> Even with no code in the repo, a well-written README signals strong technical communication — a core AI PM skill. A GitHub profile showcasing your work demonstrates skills and commitment to potential employers. 

### LinkedIn — Write Post #1 Today

**Post #1 — The Problem Post** (before building anything)
```
I'm building an AI agent for Kenyan private schools. 
Here's the problem I'm solving.

A school admin in Nairobi spends 3–4 hours every week 
copy-pasting the same WhatsApp message to 200+ parents. 
One by one. From their personal phone.

Exam dates. Fee reminders. Emergency alerts. 
All manual. All error-prone. All eating into time 
that should go toward students.

I spent this week visiting schools in Nairobi 
to understand the pain firsthand.

Here's what I heard:
- "Parents only call when they don't get the message"
- "I have 4 WhatsApp groups I manage alone"
- "I sent the wrong exam date to the wrong class once"

I'm building SchulPulse — a WhatsApp AI agent 
that automates school-to-parent communication 
for small private schools.

No app downloads. No new systems for parents to learn. 
Just WhatsApp — the tool they already use.

I'll be documenting the entire build publicly — 
from zero experience to live pilot in 6 weeks.

Follow along if you're interested in:
→ Building AI agents without code
→ EdTech in emerging markets  
→ The AI PM career transition journey

Week 1 starts now. 👇

#AIProductManager #BuildInPublic #EdTech #Kenya #SchulPulse
```

---

## PHASE 1 — DISCOVERY (Week 1–2)

### User Research: 5 Schools, 20-Minute Conversations

Your interview script (use Claude to generate variations if needed):

**For School Admin/Owner:**
- "Walk me through your Monday morning. How do you communicate with parents?"
- "What's the most painful admin task you do every week?"
- "When was the last time a communication mistake caused a problem?"
- "If you could remove one thing from your job tomorrow, what would it be?"
- "What would you pay monthly to never have to do [that thing] again?"

**Capture in Notion:** Direct quotes (with permission), pain intensity (1–5), willingness to pay signals. These quotes become the most compelling part of your case study — employers want to see real customer feedback alongside your AI integrations. 

### Deliverables by End of Week 2

**Notion:** Problem Discovery section complete with 3+ interview summaries, 2 personas, final problem statement.

**GitHub README:** Problem + Solution sections filled in.

**LinkedIn Post #2 — The Research Post:**
Share 3 anonymised quotes from school admins. Frame it as: *"I thought I knew the problem. User research changed my assumptions. Here's what I found."* Specific and human beats generic every time.

---

## PHASE 2 — DESIGN (Week 3)

### Conversation Flow Design (Your UI Skills Shine Here)

Build the full conversation map in **Figma** (free). Every path a parent can take, every response the bot gives. Think of it exactly like a UI wireframe — you already know how to do this.

**5 Core Flows for MVP:**
```
FLOW 1 — School Broadcasts Announcement
Admin fills Google Form → Make triggers → WhatsApp template → All parents in selected class

FLOW 2 — Parent Asks "FEE BALANCE"
Parent texts keyword → Make looks up Google Sheet → Returns child's balance

FLOW 3 — Parent Asks "TIMETABLE"  
Parent texts keyword → Bot returns current exam schedule

FLOW 4 — Parent Asks "HELP"
Bot returns menu of all available commands

FLOW 5 — Unrecognised Input
Claude API handles natural language → Smart short reply → Redirects to HELP if unsure
```

**Design decision to document in Notion & GitHub:**
> *"I deliberately cut report card delivery and attendance queries from MVP. Both require per-school data structures that would extend build time by 3+ weeks. Fee balance and announcements cover 80% of daily pain with 20% of the complexity. Phase 2."*

This is the kind of trade-off reasoning AI PM interviewers probe for.

### WhatsApp Message Templates (Write All 8 Now)

Submit these to Meta via Manychat for approval — takes 24–72 hours:

| # | Template Name | Category | Example |
|---|---|---|---|
| 1 | `Schulpulse_welcome` | Utility | "Welcome to SchulPulse for [School]. Reply HELP for options." |
| 2 | `Schulpulse_announcement` | Utility | "📢 [School]: {{message}}. Sent via SchulPulse." |
| 3 | `Schulpulse_fee_reminder` | Utility | "Hi {{parent_name}}, {{child_name}}'s fee balance is KSh {{amount}}. Due: {{date}}." |
| 4 | `Schulpulse_exam_alert` | Utility | "📝 Exams begin {{date}}. Timetable: {{link}}. — {{school_name}}" |
| 5 | `Schulpulse_term_dates` | Utility | "📅 Term {{term}} ends {{date}}. Next term begins {{date}}." |
| 6 | `Schulpulse_emergency` | Utility | "🚨 URGENT — {{school_name}}: {{message}}. Contact: {{phone}}" |
| 7 | `Schulpulse_report_card` | Utility | "{{child_name}}'s report is ready. View here: {{link}}" |
| 8 | `Schulpulse_optin_confirm` | Utility | "You're now receiving updates from {{school_name}} via SchulPulse. Reply STOP to opt out." |

**Note:** "Utility" category is cheapest Meta rate and covers all school admin use cases.

---

## PHASE 3 — BUILD (Weeks 4–6)

### Step-by-Step: Make Scenario for Broadcast Flow

This is your core automation. Do it exactly in this order:

**Step 1 — Build the Admin Input Form (Google Forms)**
Fields: School Name, Class/Group, Message Type (dropdown), Message Body, Schedule (Now / Date+Time), Your Name.

**Step 2 — Connect Form to Google Sheets**
Google Forms auto-populates a Sheet. Add a "Status" column manually (values: PENDING / SENT / FAILED).

**Step 3 — Build Make Scenario**
```
Module 1: Google Sheets — Watch New Rows (every 15 min)
Module 2: Filter — only proceed if Status = "PENDING"
Module 3: Manychat — Send WhatsApp Template to subscriber list
           (Map: message body → template variable)
Module 4: Google Sheets — Update row Status to "SENT"
Module 5: Google Sheets — Write timestamp to "Sent At" column
```

**Step 4 — Test Ruthlessly**
Send 10 test messages to yourself. Test: empty fields, special characters in message body, long messages, numbers not on WhatsApp. Log every failure in your Notion Build Log — this is portfolio content.

### Step-by-Step: Manychat Flows for Parent Replies

Inside Manychat's Flow Builder:
```
KEYWORD TRIGGER: "FEE BALANCE" (+ variations: "fee", "balance", "fees")
→ Action: Make Webhook (passes parent's phone number)
→ Make looks up phone number in Google Sheets
→ Returns fee data back to Manychat
→ Manychat sends reply to parent

KEYWORD TRIGGER: "HELP"
→ Manychat sends: "Hi! I'm SchulPulse 👋
   Reply with:
   FEE BALANCE — your child's fee status
   TIMETABLE — current exam schedule
   TERM DATES — upcoming term calendar
   CONTACT — school office number"

CATCH-ALL (no keyword match)
→ Route to Claude API via Make webhook
→ Claude system prompt: "You are SchulPulse, 
   a friendly assistant for [School Name] parents. 
   Answer briefly (max 2 sentences). 
   If unsure, say: 'For this, please contact 
   the school office directly on [number].'"
→ Return Claude's response to parent
```

### Adding Claude API (The AI Brain)

In Make, add an HTTP module after the catch-all trigger:
- URL: `https://api.anthropic.com/v1/messages`
- Method: POST
- Headers: `x-api-key: [your key]`, `anthropic-version: 2023-06-01`
- Body: Pass parent's message as user content, your school-specific system prompt as the system message

This is the part that makes SchulPulse an *AI agent* and not just a chatbot. Document the system prompt design in your GitHub README — prompt engineering is one of your certified skills.

---

## PHASE 4 — PILOT (Weeks 7–8)

### Pilot Metrics Dashboard (Build in Google Sheets)

Track these weekly. These numbers go into your Notion case study and LinkedIn posts:

| KPI | Target | How to Measure |
|---|---|---|
| Message delivery rate | >95% | Make scenario success logs |
| Parent opt-in rate | >70% of enrolled families | Form submissions vs. total families |
| Admin time saved/week | >2 hours | Ask admin directly, Week 1 vs. Week 4 |
| Parent reply rate to broadcasts | >15% | Manychat inbox counts |
| Bot failure rate (unhandled messages) | <10% | Manychat "no match" logs |
| Admin satisfaction (1–5) | ≥4 | End-of-pilot survey |

### Pilot Launch Day Checklist

- [ ] All 8 templates approved by Meta
- [ ] 20+ parents opted in via Google Form
- [ ] Admin trained (30-minute walkthrough, record it for your portfolio)
- [ ] You monitoring Make logs in real time for first 4 hours
- [ ] Direct line open with admin for immediate issue reporting

---

## PHASE 5 — PORTFOLIO ASSEMBLY (Week 9)

### Notion Case Study — Final Polish Checklist

- [ ] Problem section has 3+ direct quotes from school admins
- [ ] User personas have photo (use UI Faces or similar), name, quote, goals, frustrations
- [ ] Tech stack table includes *why* each tool was chosen (not just what it is)
- [ ] Build Log has at least one documented failure and how you fixed it — employers respect honesty
- [ ] KPI dashboard screenshot from live pilot
- [ ] Section 07 "AI PM Competencies Demonstrated" explicitly maps your work to PM skills: discovery, prioritisation, system design, prompt engineering, metrics, iteration

### GitHub README — Final Polish Checklist

- [ ] Architecture diagram (annotated Make screenshot)
- [ ] Conversation flow diagram (Figma export)
- [ ] All 8 WhatsApp templates listed
- [ ] 3–5 key product decisions with explicit rationale
- [ ] Pilot metrics with real numbers
- [ ] Clear "What I'd Build Next" section

### LinkedIn Post #6 — The Closing Post

This is your most important post. Write it *after* the pilot. Formula:
```
6 weeks ago I had zero experience building AI agents.
[Today's result — one specific, concrete metric]

Here's the full story of building SchulPulse 👇

THE PROBLEM: [1 sentence, quantified]
THE INSIGHT: [1 thing user research revealed that surprised you]
THE BUILD: [Stack in one line + biggest technical challenge you overcame]
THE RESULT: [2–3 pilot metrics]
THE LESSON: [1 honest, specific thing you'd do differently]

Full case study: [Notion link]
GitHub: [Repo link]
Demo video: [Loom link]

If you're an AI PM, EdTech founder, or building 
in emerging markets — I'd love to connect.

#AIProductManager #BuildInPublic #SchulPulse #EdTech
