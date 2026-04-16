# Step 1 — UX Exploration: Social Stream
## Feature: Social Posts (Social Stream)
**Date:** April 12, 2026
**Practice Used:** North Park Vision (#1813, location 2274)
**Admin URL:** `app.patientengage.ai/a/social-stream`
**Practice URL:** `app.patientengage.ai/u/{id}/marketing/social/{locationId}`

---

## What Is Social Stream?

Social Stream is PatientEngage's automated social posting system. It publishes branded, eye-care-relevant content to a practice's Facebook, Instagram, and Google Business Profile pages on a weekly schedule — with zero effort from the practice.

Social Stream posts are **separate from Campaign Posts**. Campaigns (One-Click Campaigns feature) also generate social posts, but those are tied to specific campaigns. Social Stream is the always-on, background content engine.

---

## How It Works — Admin Side [OBSERVED]

### Streams
There are **9 active streams** as of March 2026:

| Stream | Posts/Month | Locations Subscribed |
|---|---|---|
| EyeCarePro (main) | 4 | 731 |
| AEG | 2 | 594 |
| Specialty: Dry Eye | 2 | 102 |
| Specialty: Sclerals | 1 | 75 |
| Specialty: Vision Therapy | 2 | 36 |
| Specialty: Sports Vision | 2 | 28 |
| ProVision | 4 | 10 |
| Glemaud | 1 | 44 |
| 20/20 Image Eye Centers | 4 | 9 |

**Total:** 22 Social Stream Posts scheduled in March 2026 [OBSERVED]

### Stream Management
- Admin page at `/a/social-stream` shows a monthly calendar view
- "Stream" dropdown lets admin switch between streams
- "MANAGE STREAMS" and "MANAGE SUBSCRIPTIONS" buttons at top
- Posts appear on the calendar as thumbnail + title + time

### Post Creation (Admin)
Each post is created at `/a/social-stream/post/{id}` with:

- **Title** — internal label (e.g., "Seasonal Allergies")
- **Content type tabs:** Image | Video | Text Only
- **Post to toggles:**
  - Facebook (with optional CTA link → "Practice Website" dropdown)
  - Google Business Profile (with optional CTA link)
  - Instagram
- **Date & Time (EST)** — scheduled post time
- **Countries (Optional)** — geographic targeting
- **Content** — rich text editor (Powered by Tiny), ~44 words typical
  - Has "Placeholder" dropdown for dynamic practice tokens
- **Facebook / Google Post Image(s)** — image upload
- **Instagram Image(s)** — separate image upload for IG format
- **DELETE / SAVE** buttons

**Key insight:** Facebook and Google share the same image, but Instagram gets its own separate image upload. This allows for platform-optimized formatting (landscape for FB/Google, square for IG).

---

## How It Works — Practice Side [OBSERVED]

### Social Stream Calendar View
The practice sees their Social Stream at `Marketing > Social`.

**Page title:** "Social Stream" with back arrow

**Left sidebar contains:**
1. **Month/year navigator** — "March 2026" with < > arrows
2. **Filter checkboxes:**
   - ☑ Social Stream Posts (checked by default)
   - ☐ Campaign Posts - Facebook
   - ☐ Campaign Posts - Instagram
   - ☐ Campaign Posts - GMB
3. **CONNECT INSTAGRAM** button (if not connected)
4. **Facebook Insights** — Likes, Comments, Shares, Impressions
5. **Instagram Insights** — similar metrics

**Calendar grid:** Standard Sun–Sat monthly calendar showing post thumbnails with:
- Post image thumbnail
- Post title
- Post time (e.g., "9 am EST" or "3 pm EST")
- Color-coded left border (teal for Social Stream, blue for Campaign)

### Filter Behavior [OBSERVED]
When only "Social Stream Posts" is checked, the calendar shows the EyeCarePro stream posts (weekly, Wednesday at 9 am EST) plus any specialty stream posts.

When "Campaign Posts - Facebook" is also checked, the calendar fills up significantly — campaign-generated Facebook posts appear (typically Mon at 3 pm EST, weekly during active campaigns).

**North Park Vision March 2026 — combined view showed ~12–15 posts** across Social Stream and Campaign sources. Key posts observed:

| Date | Source | Title | Time |
|---|---|---|---|
| Mon Mar 2 | Campaign | (glasses/exam image) | 3 pm EST |
| Wed Mar 4 | Social Stream | Seasonal Allergies | 9 am EST |
| Thu Mar 5 | Specialty Stream | Dry Eye | 9 am EST |
| Mon Mar 9 | Campaign | Silent Signs of Diabetic Eye Disease | 3 pm EST |
| Tue Mar 10 | Specialty Stream | Sports Vision | 9 am EST |
| Wed Mar 11 | Social Stream | Save Your Vision Month | 9 am EST |
| Thu Mar 12 | Specialty Stream | Vision Therapy | 9 am EST |
| Mon Mar 16 | Campaign | (eye health topic) | 3 pm EST |
| Tue Mar 17 | Specialty Stream | Dry Eye | 9 am EST |
| Wed Mar 18 | Social Stream | New Season New Glasses | 9 am EST |
| Wed Mar 25 | Social Stream | UV Protection | 9 am EST |

### Connection Warnings [OBSERVED]
- Warning banner: "⚠ Warning: Instagram connection required to post for this location."
- Practice sees "CONNECT INSTAGRAM" button prominently displayed
- Facebook Insights show "Likes: 0" for this practice (low engagement)

---

## Key UX Observations

1. **Zero-effort value:** Practices see a calendar full of posts they didn't create. The Social Stream runs automatically in the background.

2. **Unified calendar:** Social Stream posts AND Campaign posts appear on the same calendar, giving the practice a complete view of their social presence.

3. **Multi-source, multi-channel:** A practice subscribed to the main EyeCarePro stream plus 3 specialty streams gets 4+ posts/week from Social Stream alone, plus additional Campaign posts.

4. **Connection friction:** The "CONNECT INSTAGRAM" warning and button suggest many practices haven't completed Instagram setup. The Social Connections report confirms only 20% have Instagram connected.

5. **Content is pre-written:** All post content is managed by EyeCarePro admins — professional copy (~44 words), curated imagery, scheduled times. The practice doesn't write anything.

6. **Seasonal/topical content:** March posts included Seasonal Allergies, Save Your Vision Month, UV Protection, Dry Eye, Sports Vision — all timely and relevant to optometry.

---

## Practice Navigation Path
`Dashboard > Marketing (left nav) > Social` → Social Stream page

The practice's left nav shows:
- Main
- Settings  
- Help

The Social Stream is accessed from the Marketing section of the main dashboard.

---

## Provenance Notes
- All UI elements, page layout, filter behavior: [OBSERVED] from live dashboard
- Post titles and schedule: [OBSERVED] from North Park Vision calendar view
- Post edit form structure: [OBSERVED] from admin post detail `/a/social-stream/post/5137`
- Connection warning text: [OBSERVED] verbatim from practice view
