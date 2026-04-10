# Step 1: UX Exploration — Campaigns-To-Go

**Feature:** Campaigns-To-Go (Multi-Channel Marketing Campaigns)
**Feature URL (Practice View):** `/u/{practiceId}/marketing/campaigns`
**Admin Report URL:** `/v2/a/reports/campaigns`
**Admin Manager URL:** `/a/campaigns-management`
**Date:** April 10, 2026
**Data Reference Period:** March 2026

---

## Mode 1 — The Before State

### What practices do WITHOUT Campaigns-To-Go:

**The Process:** They have a staff member "trying" to post to Facebook once a month when it isn't busy. They manually export CSV files from their EHR (if they even know how) to send a "Happy Holidays" email once a year.

**The Technical Problem:** Fragmented tools. A landing page that doesn't talk to an email, which doesn't talk to a social post. No system connects these efforts — each platform is its own silo.

**The Business Problem:** They are ghosting their own patient base. Their "breadcrumb trail" is cold. They are losing second-pair sales and specialty revenue because they aren't "top of mind" when the patient actually has the money.

**The Impact:** Revenue leakage. High patient churn. They are paying a "lazy tax" by not automating their outreach.

### The Three Before States:

1. **The Do-Nothing Practice:** They know they should market but never start. Last Facebook post was 3 months ago. No email list. No landing pages. They rely entirely on Google and word-of-mouth — and wonder why patient volume is flat.

2. **The Sporadic Poster:** A front desk member "does social media" when the schedule is slow. They post a stock photo with "Happy National Sunglasses Day!" once a quarter. No email campaigns. No landing pages. No way to measure if it works.

3. **The Overinvesting Practice:** They pay an agency $2,000–$5,000/month for generic healthcare marketing. The agency sends them monthly "reports" full of vanity metrics (impressions, reach) with zero connection to actual appointments. They can't tell if the spend is working.

---

## Mode 2 — Data Landscape Survey

**Practice explored:** North Park Vision (Account #1813)
**URL:** `/u/1813/marketing/campaigns`

### Practice Dashboard Context

The practice dashboard (`/u/1813/dashboard`) organizes features into categories. Campaigns lives under the **Marketing** section alongside Social Posts, Landing Page, and Google Ads. Other sections: Communications (Forms, Text Messages, Announcements), Local SEO (Reviews, Google Profile, Google Reserve, Facebook, Directory Listings), and My Practice.

### Campaigns List View — What the Practice Owner Sees

The main campaigns page is organized into three sections:

**Live Campaigns (1):** "April Sports Eye Safety Month" — Apr 6 to Apr 30 — 12 posts, 1 email. Campaign card shows a professional graphic (golfer with "April is Sports Eye Safety Awareness Month" text).

**Future Campaigns (1):** Horizontal calendar timeline showing months (May through October 2026). May has "GENERIC - DIABETIC EYECARE" (May 4 to May 29, 12 posts, 1 email) already scheduled. June through October show empty slots with blue "ADD CAMPAIGN" links — creating a natural call-to-action to fill the calendar.

**Past Campaigns (74):** Horizontal scrolling timeline showing campaigns by month:
- March 2026: "Diabetes - Did You Know?" (12 posts, 1 email)
- February 2026: "Preventive Eye Care Tips for Every Age" (12 posts, 1 email)
- January 2026: "New Year Raise Your Glasses" (9 posts, 1 email)
- December 2025: "Ferragamo - UIOLI - Marchon" (12 posts, 1 email)
- December 2025: "UIOLI - Family Centered" (12 posts, 1 email)
- November 2025+: continues scrolling back

**Standard campaign structure:** 12 social posts + 1 email blast + 1 poster + 1 landing page + 1 Facebook cover per month.

**Header buttons:** SETTINGS (dropdown) and ADD CAMPAIGN (dropdown). SETTINGS dropdown reveals 5 channel configuration categories: Google, Facebook, Instagram, Emails, EHR. Setup is extremely easy. ADD CAMPAIGN is the entry point for selecting a new campaign.

### ADD CAMPAIGN Flow — The Campaign Library

**Step 1:** Click ADD CAMPAIGN → dropdown shows available months with campaign counts (e.g., "April 2026 (1)", "June 2026 (0)").

**Step 2:** Select a month → navigates to campaign library (`/u/{id}/marketing/campaigns/new/2026/June`). The library is organized into two sections:
- **Top section:** Brand-sponsored campaigns (Nike Back To School = 116 Launches Total, Lacoste Back To School = 93 Total, MARCHON-NIKE-USE IT OR LOSE IT = 72 Total, World Sight Day Nike = 61 Total, etc.)
- **"New" section (24 campaigns):** Clinical/generic campaigns (GENERAL - ANNUAL EYE EXAMS = 54 Launches in June, GENERAL - DRY EYE - LLL, GENERAL - MYOPIA AWARENESS, GENERIC - MYOPIA SPECTACLE THERAPY, GENERIC - IPL FOR DRY EYE RELIEF, GENERIC - MEIBOMIAN GLAND DYSFUNCTION, etc.)

Each campaign card shows: campaign name, professional thumbnail image, "X Launches in June" (current month adoption), and "X Launches Total" (all-time network adoption — social proof).

**Access note:** The campaign library is filtered by group/brand access. Practices only see campaigns available to their network group — not the full catalog. Brand-specific campaigns (Nike, Lacoste, Marchon) are restricted to practices in those brand groups. The admin view shows all campaigns across all groups.

**Step 3:** Click a campaign → preview all assets (Previous/Next navigation through Email, Landing Page, Social Posts, etc.). Email preview shows branded email with practice name, phone, "Book Eye Exam" CTA, and campaign creative. Includes Send Preview, Copy HTML, and Schedule Campaign buttons.

**Step 4:** Click Schedule Campaign → **Confirm Campaign Dates** modal:
- **Dates:** Start/End date pickers (defaults to month boundaries)
- **Locations:** Multi-select checklist of all practice locations (with Deselect All)
- **Confirm Campaign Channels:** Toggle switches for Facebook Posts, Facebook Cover, Instagram Posts, Google My Business Posts (all on by default)
- **Email Channel Settings:** Toggle switches for EHR Automated (requires support to enable Ninja EHR Email), Uploaded List, 3rd party systems. Setup EHR Connection button.
- **Approval Needed:** Toggle (on = requires admin approval before sending)
- **Email marketing 1:** Date picker + Time picker (e.g., "6/1/2026, 11:00 AM EST")
- **Schedule Campaign** button (red, prominent)

**Key UX insight:** The entire flow from "I want to market" to "campaign scheduled across all channels" is 4 clicks: ADD CAMPAIGN → pick month → browse & select → confirm & schedule. No content creation, no design work, no platform switching.

### Campaign Detail View — "Diabetes - Did You Know?" (Campaign #75237)

**Header:** Campaign name with DELETE (red), SETTINGS, ADD, and VIEW buttons.
**Dates:** Start: 2026 Mar 02 / End: 2026 Mar 31 / Status: Ended

#### Impressions Section

| Metric Name (UI) | Value Observed | What It Measures | Marketing Potential Type |
|-------------------|---------------|-----------------|------------------------|
| Emails Sent | 6,724 | Total emails delivered to this practice's patient list | Volume: "X emails sent per campaign" |
| Bounces | +10 | Emails that failed to deliver | Deliverability: low bounce = clean list |
| Email Clicks | 30 (0.4%) | Patients who clicked a link in the campaign email | Engagement: "X% clicked through" |
| Facebook Impressions | 16 | Times the Facebook post was shown in feeds | Volume / Reach |
| GMB Clicks | 0 | Clicks on the Google Business Profile post | Engagement |
| Instagram Impressions | 0 | Times the Instagram post was shown | Volume / Reach (not enabled for this practice — practices can elect not to use a channel or it wasn't hooked up) |

#### Views Section

| Metric | Value | What It Measures | Marketing Potential Type |
|--------|-------|-----------------|------------------------|
| Emails Opens | 2,314 | Patients who opened the campaign email (34.4% open rate) | Engagement: "34% of patients opened" |
| Landing Page Views | 97 | Visits to the campaign's dedicated landing page | Engagement: "X patients visited the page" |

#### Appointments Section — "Appointments within 7 days email events"

| Metric | Value | What It Measures | Marketing Potential Type |
|--------|-------|-----------------|------------------------|
| Appts from Clicks | 2 (0 Completed) | Appointments booked within 7 days by patients who clicked | Revenue: direct click → appointment attribution |
| Appts from Opens | 100 (14 Completed) | Appointments booked within 7 days by patients who opened | Revenue: open → appointment attribution |

**⚡ Killer Stat Candidate:** 100 appointments attributed to a single campaign at a single practice from email opens alone. 14 already completed. This is the metric that ties campaign activity directly to revenue.

#### EHR Patient Filter (Pre-Send Targeting)

The campaign detail view includes a patient filter section with these fields:
- Age From / Age To
- Last Appointment From / Last Appointment To
- Zip Code / City
- Insurance Company / Insurance Type (dropdown)
- Gender (dropdown)
- Shows estimated patient count: "~8,273 Patients"
- SAVE button to apply filter

**This is pre-send targeting** — practices can optionally use these filters to narrow which patients receive the campaign email. This means campaigns can be segmented by demographics, geography, insurance, and appointment recency.

#### Multi-Channel Content Timeline (Per Location)

**Location: North Park Vision Center, PC**

The timeline shows every asset and its delivery schedule. For the Diabetes campaign:

| Date/Time | Channel | Asset | Metrics |
|-----------|---------|-------|---------|
| (Campaign start) | Landing Page | "Stay Ahead of Diabetic Eye Disease" page | ✅ 97 Views |
| (Campaign start) | Facebook Cover | "Silent Signs of Diabetic Eye Disease" banner | (auto-set) |
| Mar 02, 12pm EST | Email | Campaign email blast | 6,724 Sent / 34.4% Opened / 0.4% Clicked |
| Mar 02, 3pm EST | Facebook | Social post | ✅ 6 Impressions, 0 Engagements |
| Mar 02, 3pm EST | Google (GBP) | Business Profile post | ✅ 0 Clicks |
| Mar 09, 3pm EST | Facebook | Social post | ✅ 4 Impressions, 0 Engagements |
| Mar 09, 3pm EST | Google (GBP) | Business Profile post | ✅ 0 Clicks |
| Mar 16, 3pm EST | Facebook | Social post | ✅ 2 Impressions, 0 Engagements |
| Mar 16, 3pm EST | Google (GBP) | Business Profile post | ✅ 0 Clicks |
| Mar 23, 3pm EST | Facebook | Social post | ✅ 4 Impressions, 0 Engagements |
| Mar 23, 3pm EST | Google (GBP) | Business Profile post | ✅ 0 Clicks |
| Mar 30, 8pm | Facebook | Reset Cover | ✅ Posted |

**Total from one campaign selection:** 1 landing page + 1 email blast + 1 poster + 1 Facebook cover + 4 weekly Facebook posts + 4 weekly GBP posts + 1 cover reset = **coordinated multi-channel assets across 3+ channels** from a single campaign selection. No Instagram in this campaign (not enabled for this practice — practices can elect not to use a channel or it wasn't connected). Full campaign structure = 12 social posts + 1 email + 1 poster + 1 landing page + 1 Facebook cover.

Each asset shows a thumbnail of the creative, the channel icon (blue Facebook, red Google G, email envelope), the scheduled date/time, and per-asset metrics (Impressions, Engagements, Clicks, Sent/Opened/Clicked).

### Settings & Configuration

- **SETTINGS dropdown** on campaigns list page reveals 5 channel categories: Google, Facebook, Instagram, Emails, EHR
- Social channel authorization is per-practice (OAuth connections)
- Channel participation is optional — practices can elect not to use a channel
- No DIY content editor — campaigns are selected from a pre-built library, not created by the practice
- Campaign scheduling is per-month with start/end dates
- EHR Patient Filter provides optional pre-send segmentation by demographics

### Actions Staff Can Take

1. Browse and select campaigns from the ADD CAMPAIGN dropdown
2. Schedule a campaign for a specific month
3. View campaign performance (impressions, views, appointments)
4. Filter campaign recipients using EHR Patient Filter (optional pre-send targeting)
5. Connect/configure social channels via SETTINGS
6. Delete a campaign
7. View campaign assets and landing page via VIEW button
8. Search past campaigns

### Admin Campaigns Report (`/v2/a/reports/campaigns`)

The admin report is the network-wide view used by EyeCarePro's team.

#### Summary Bar
- Campaigns count, Practices count (with MoM trend %), Locations count (with MoM trend %)

#### Performance Card Metrics

| Metric Name (UI) | What It Measures | Time Period | Marketing Potential Type |
|-------------------|-----------------|-------------|------------------------|
| Emails Sent | Total emails sent across all practices for selected month | Monthly | Volume: "3.7M emails sent per month" |
| Opens (Unique) | Unique patients who opened at least one campaign email | Monthly | Engagement: "21% open rate" |
| Opens (Total) | Total opens including repeat opens by same patient | Monthly | Engagement (depth) |
| Email Clicks | Total clicks on links within campaign emails | Monthly | Engagement: "0.6% CTR" |
| Page Views | Total landing page views from all campaigns | Monthly | Engagement: "62K landing page visits" |
| EHR Email Appts | Appointments booked within 7 days of email events | Monthly | Revenue: "34,623 appointments attributed to campaigns" |

#### Alerts Card

| Alert | What It Flags | Marketing Potential |
|-------|---------------|-------------------|
| No Email | Practices with campaigns but no emails sent | Operational health: "99.X% delivery success" |
| No Page Views | Campaigns with zero landing page visits | Content engagement |
| Bounce > 5% | Practices exceeding bounce threshold | Deliverability proof: "Only 1 practice flagged" |
| Complaints > 0.1% | Practices exceeding complaint threshold | Trust: "Only 4 practices flagged" |

#### Practice Table Columns
Practice, Campaign, Social (post count), Emails Sent, Total Opens, Unique Opens, Bounces, Complaints, Email Clicks, Page Views

#### Filters
All Groups, All CSs/MMs, Month/Year picker, Search, CSV Export

### Admin Campaigns Manager (`/a/campaigns-management`)

#### Performance Card
- Completed, Live, Scheduled (campaign status counts)
- Emails Scheduled, Emails Sent

#### Alerts Card
- No Campaign, Emails Queued, Emails Processing, Emails Not Sent, Needs Approval

#### Practice Scheduling Table Columns
Practice Name, State, Group, Campaign Name, EHR type, Send Date, Action

#### Action Types
- **ECP Scheduler** — Scheduled by EyeCarePro's team
- **External Link** — Practice manages own scheduling
- **Request Form** — Requires a request form submission
- **VSP Scheduler** — Scheduled through VSP's system
- **SCHEDULE button** — Needs to be scheduled (action needed)

### EHR and Third-Party Integrations Visible
- EHR type column in admin tables (Office Mate, Crystal PM, etc.)
- Social channel connections (Facebook, Instagram, Google Business Profile — per practice, optional)
- Landing page generation (auto-created per campaign)

---

## Mode 3 — The Workflow Narrative

### The Morning Scenario (Grounded in North Park Vision Walkthrough)

At 9:00am, the office manager at North Park Vision opens the Campaigns tab and sees her campaign calendar at a glance — the April "Sports Eye Safety Month" campaign is live (Apr 6–30, 12 posts, 1 email), and the May "Diabetic Eyecare" campaign is already scheduled and waiting in the Future Campaigns timeline. She clicks into last month's "Diabetes - Did You Know?" campaign and immediately sees that 6,724 emails went out, 2,314 patients opened them (34.4% open rate), and 30 clicked through to the landing page — which got 97 views. Below that, the Appointments section shows 100 patients booked an exam within 7 days of opening the email, with 14 already completed. She scrolls down and sees the full timeline: every Facebook post, every Google Business Profile post, the landing page — all 12 assets that fired across 3 channels from a single campaign selection. She didn't write any of it, design any of it, or schedule any of it individually. She looks at the Future Campaigns row: June through October are empty with "ADD CAMPAIGN" links. She clicks ADD CAMPAIGN for June.

### The Aha Moment

The moment you see the multi-channel content timeline in the campaign detail view — a single campaign selection automatically generated and scheduled 1 landing page + 1 email blast + 1 Facebook cover + 4 weekly Facebook posts + 4 weekly GBP posts + 1 cover reset. Twelve coordinated assets across three channels. The practice didn't write a word of copy, design an image, or log into three different platforms. The aha is the gap between what this replaces (Facebook login + Google login + email platform + landing page builder + weekly scheduling = hours of work) and what it actually took (browse, select, done).

### The Relief Moment

Seeing "100 Appts from Opens (14 Completed)" on the campaign detail page. This is the moment the practice owner stops wondering if marketing works. They can see the line from "campaign email sent" to "patient in the chair." Every other marketing tool they've used showed them opens and clicks — vanity metrics. This shows them appointments with completion status. That's the relief: they finally have proof, and it's specific enough to calculate ROI.

### The Embarrassment Moment

When the practice owner sees that North Park Vision has run 74 past campaigns — one every month for over 6 years — while their practice hasn't sent a single coordinated campaign. Or when they see the "~8,273 Patients" count in the EHR filter and realize every month without a campaign is a month where 8,000+ patients hear nothing from them. The Future Campaigns calendar with empty June–October slots makes the gap painfully visible.

### The Dinner Party Sentence

"We used to struggle to post anything to social media — now we run professional campaigns across email, Facebook, and Google with one click, and we can actually see which ones bring patients in. Last month's campaign put 100 patients back on our schedule."

---

## Mode 4 — Emotional Mapping

### 1. The "Before State" Emotions (The Malignancy)

Practice owners don't just have "bad marketing"; they have a deep-seated anxiety rooted in three specific areas:

**The Invisibility Fear:** "I spent $2M on this build-out and my equipment, but if my EHR died tomorrow, would anyone remember I exist?"

**The Staff Resentment:** "I pay my front desk $22/hour to be the face of my brand, but they are 'too busy' to send an email or post to Instagram. I feel like I'm paying for a car that won't start."

**The "Imposter" Anxiety:** They see the flashy "Crizal" or "Myopia" ads from corporate competitors. They feel small, outdated, and technically illiterate compared to the "big guys."

### 2. The "Neighbor Test" (The Competitive Shame)

**The Scenario:** A patient of 5 years mentions they just bought their second pair of glasses at the "new place down the street" or online because they saw a 20% off ad.

**The Emotion:** Betrayal and embarrassment. The owner feels like they failed to "protect" their patient base.

**The Gap:** They realize their "relationship" wasn't enough to beat a well-timed digital nudge.

### 3. The "What If It Broke?" Test (The Vulnerability)

**The Question:** "If your front desk lead quit today, how would you tell your patients about your new dry eye service?"

**The Reality:** Total paralysis. Most practices realize their entire marketing "system" is actually just one person's Google login and a "hope for the best" attitude.

**The Relief:** EyeCarePro Campaigns moves the "system" from a person's head into an automated machine.

### 4. The "Future State" Relief (The Pill)

**Predictability:** The "weight off the shoulders" when they realize the EHR is doing the heavy lifting.

**Authority:** Walking into the exam room knowing the patient has already read the email about Scleral lenses. They aren't "selling" anymore; they are "consulting."

**Pride:** Seeing a professional, high-end landing page that actually looks as good as their clinical skills.

### 5. Emotional Pivot Summary

| Trigger | Current Emotion | Future Emotion |
|---------|----------------|----------------|
| New Specialty | Overwhelmed / "How do I start?" | Confident / "The system handles it." |
| Staff Workload | Frustration / Micro-managing | Freedom / Trust in automation. |
| Patient Churn | Fear / Scarcity | Abundance / Retention. |
| Competition | Defensive / Vulnerable | Proactive / Dominant. |

---

## Mode 5 — Strategic Classification & Marketing Translation

### Strategic Classification

To sell Campaigns effectively, you must stop treating it as a "social media tool" and start treating it as a **Revenue Recovery Engine**.

**Primary Category: Efficiency & Retention (The "Leaky Bucket" Fix)**
Justification: While Campaigns can assist in acquisition, its primary business function is maximizing the Lifetime Value (LTV) of the existing patient database. It automates the "middle of the funnel" where 80% of revenue leakage occurs in optometry (unsold second pairs, forgotten follow-ups, and unbooked specialty candidates).

**Secondary Category: Engagement & Authority (The "Consultant" Builder)**
Justification: By warming up patients with EHR-segmented educational content before they arrive, it reduces chair-time friction and increases the "acceptance rate" of medical recommendations.

### The "Killer Stat" Framework (Proof Points)

**1. The Ghosting Rate (Database Decay):**
- The Question: "Out of the 5,000+ patients in your EHR, how many have received a personalized, medical-grade communication from you in the last 90 days?"
- The Proof: Most practices "ghost" 95% of their database. This represents a massive untapped asset that is currently depreciating.

**2. The Manual Labor Tax (Operational Waste):**
- The Question: "What is the hourly cost of your front desk staff spending 3-5 hours a week trying to 'do marketing' (designing, exporting CSVs, posting) that results in zero trackable ROI?"
- The Proof: Campaigns costs $49/mo. If their staff spends just 3 hours a month at $20/hr failing at this, they are already losing money ($60 vs $49).

**3. The Capture Gap (Revenue Leakage):**
- The Question: "If an automated Myopia or Dry Eye campaign reached your current patients and just 1% booked an evaluation, what would that do to your gross revenue this month?"
- The Proof: For an average practice with 5,000 patients, a 1% conversion is 50 exams. At a $300 specialty average, that's $15,000 in "found" revenue for a $49 investment.

### Marketing Translations

From Mode 1 observations:
- **Observation:** Staff members "try" to post to Facebook when it's not busy; they manually export CSVs for one email a year.
  **This means** the bar to beat is near-zero — Campaigns doesn't need to be perfect, it just needs to exist consistently.
- **Observation:** Fragmented tools — landing page doesn't talk to email, email doesn't talk to social.
  **This proves** the value isn't just convenience; it's coordination. Five channels from one click replaces five logins, five platforms, five separate efforts.
- **Observation:** Practices are paying a "lazy tax" — losing revenue by not automating outreach.
  **This means** Campaigns should be positioned as a revenue recovery tool, not a marketing nice-to-have.

From Mode 2 observations:
- **Observation:** The campaign detail view shows "Appointments within 7 days of email events" — direct attribution from campaign to booked exam.
  **This proves** Campaigns can claim something no generic email tool can: actual ROI measurement tied to patient visits, not just opens and clicks.
- **Observation:** The admin report shows near-zero bounce (1 practice) and near-zero complaint rates (4 practices) across 3.7M emails.
  **This proves** the infrastructure is enterprise-grade — practices don't need to worry about deliverability or getting flagged as spam.
- **Observation:** One campaign selection fires 12 social posts + 1 email + 1 poster + 1 landing page + 1 Facebook cover across Email + Facebook + Instagram + GBP + Landing Page simultaneously — all scheduled, all branded.
  **This means** the headline comparison isn't "Campaigns vs. Mailchimp" — it's "Campaigns vs. hiring a marketing coordinator." Four clicks replaces an entire marketing department's weekly output.

From Mode 3 observations:
- **Observation:** The office manager's entire campaign interaction is: open tab → see what's running → check appointments generated. No content creation required.
  **This proves** the "zero staff time" claim is real, not aspirational. The workflow literally doesn't include writing, designing, or scheduling social posts.
- **Observation:** The embarrassment moment — seeing automated campaigns outperform manual efforts by orders of magnitude.
  **This means** the case study angle should lean into the contrast: "What your front desk does in 5 hours, Campaigns does in one click."

From Mode 4 observations:
- **Observation:** The "Invisibility Fear" — practice owners worry patients would forget they exist without active marketing.
  **This means** the hero messaging should address the fear directly: "Your patients haven't forgotten you — but are you giving them a reason to come back?"
- **Observation:** The "Neighbor Test" — losing a patient to a competitor's well-timed ad triggers betrayal and embarrassment.
  **This proves** the urgency angle: every month without campaigns is a month where competitors are reaching YOUR patients.

---

## Metric Expected to Matter Most (Pre-Data)

**EHR Email Appointments** — the metric that ties campaign sends directly to booked exams. This is the only metric in the entire Campaigns system that bridges marketing activity to clinical revenue. At the network level (March 2026), 34,623 appointments were attributed to campaign emails. This is expected to be the killer stat, pending validation with real case study data in Step 3.

**Note:** This is a metric TYPE identification, not a committed killer stat. The actual number and framing will be determined after Steps 2 and 3 provide real, validated data.
