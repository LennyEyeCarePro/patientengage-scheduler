# Product Knowledgebase: Social Posts (Social Stream)

## Source
- PatientEngage Admin: app.patientengage.ai/a/social-stream
- PatientEngage Admin: app.patientengage.ai/a/social-reports/locations
- PatientEngage Admin: app.patientengage.ai/a/social-reports/streams
- PatientEngage Admin: app.patientengage.ai/a/social-connections
- Practice-level view: app.patientengage.ai/u/{id}/marketing/social/{locationId}
- Data period: March 2026

## Product Positioning
**Product Name:** Social Stream (internal) / Social Posts (feature category)
**Category:** Marketing (alongside Campaigns, Google Profile, Google Reviews in PE nav)
**Core Purpose:** Give practices a professional, consistent social media presence across Facebook, Instagram, and Google Business Profile — without requiring them to create, design, write, or schedule any content.

### Key Messaging
- Automated social content publishing to 3 channels simultaneously
- Professionally curated, eye care-specific content (not generic templates)
- 9 specialized content streams (general + clinical specialties)
- Platform-optimized images (landscape for Facebook/Google, square for Instagram)
- Zero practice effort after initial account connection
- Unified calendar showing Social Stream + Campaign social posts together

## How It Works
1. **Connect:** Practice connects their Facebook page, Instagram business account, and/or Google Business Profile to PatientEngage (one-time setup)
2. **Subscribe:** Practice is automatically subscribed to the main EyeCarePro content stream. Practices offering specialty services can add specialty streams (Dry Eye, Vision Therapy, Scleral Lenses, Sports Vision).
3. **Publish:** Content team creates posts at the admin level. Posts automatically publish to all subscribed practices' connected channels on the scheduled date/time.
4. **Track:** Practice sees all posts on a unified calendar with Facebook Insights (Likes, Comments, Shares, Impressions) and Instagram Insights in the sidebar.
5. **Monitor:** Admin Social Reports and Social Connections dashboards track network-wide performance and connection health.

### Important Distinctions
- **Not Campaign social posts** — Social Stream runs independently of One-Click Campaigns. Campaigns generate their own social posts (Campaign Posts). Social Stream is the always-on background engine.
- **Not DIY** — Practices don't create content. Everything is pre-built by the content team.
- **Not email** — Social Posts is social media only. For email outreach, use One-Click Campaigns.
- **Not a scheduling tool** — Practices don't schedule posts. The admin schedules; practices receive.
- **Stream-based, not post-based** — Practices subscribe to streams (content channels), not individual posts.

## Feature List
1. Automated social content publishing (Facebook, Instagram, Google Business Profile)
2. 9 specialized content streams (EyeCarePro main, AEG, Dry Eye, Vision Therapy, Scleral Lenses, Sports Vision, ProVision, Glemaud, 20/20 Image Eye Centers)
3. Platform-optimized images (separate uploads for Facebook/Google landscape + Instagram square)
4. Practice-level Social Stream calendar view with filters
5. Unified calendar combining Social Stream Posts + Campaign Posts
6. Facebook Insights sidebar (Likes, Comments, Shares, Impressions)
7. Instagram Insights sidebar
8. Social Connections health monitoring (connected, broken, available, not connected)
9. Admin Social Reports — Locations view (network performance)
10. Admin Social Reports — Streams view (per-stream performance)
11. Admin Social Stream management with calendar view
12. Admin stream management (MANAGE STREAMS, MANAGE SUBSCRIPTIONS)
13. Post creation with rich text editor (Powered by Tiny)
14. Placeholder/merge field support for dynamic practice tokens
15. Country-based geographic targeting (optional)
16. CTA link configuration per channel (Facebook, Google — "Practice Website" dropdown)

## Admin Platform Deep-Dive

### Social Stream Admin (/a/social-stream) [OBSERVED]
**Purpose:** Create and manage social content streams
**UI Elements:**
- Monthly calendar view showing scheduled posts as thumbnail + title + time
- "Stream" dropdown to switch between streams
- "MANAGE STREAMS" button — manage stream configurations
- "MANAGE SUBSCRIPTIONS" button — manage which practices subscribe to which streams

### Post Creation (/a/social-stream/post/{id}) [OBSERVED]
**Fields:**
- Title (internal label)
- Content type tabs: Image | Video | Text Only
- Post to toggles: Facebook (with CTA link), Google Business Profile (with CTA link), Instagram
- Date & Time (EST)
- Countries (optional geographic targeting)
- Content — rich text editor (~44 words typical)
- Placeholder dropdown for dynamic practice tokens
- Facebook / Google Post Image(s) — image upload (shared between FB and Google)
- Instagram Image(s) — separate image upload for IG format
- DELETE / SAVE buttons

**Key insight:** Facebook and Google share the same image (landscape), but Instagram gets its own separate image upload (square). This allows platform-optimized formatting.

### Social Report — Locations (/a/social-reports/locations) [OBSERVED]
**Performance Card (March 2026):**
| Metric | Value |
|---|---|
| Facebook Total | 174,401 |
| Instagram Total | 39,708 |
| Google Clicks | 400 |
| Location Posts | 7,098 |
| Total Interactions | 214,509 |

**Alerts Card:**
| Metric | Value |
|---|---|
| No Interactions | 1,663 |

**Scale:**
| Metric | Value |
|---|---|
| Total Practices | 1,929 |
| Total Locations | 2,696 |

### Social Report — Streams (/a/social-reports/streams) [OBSERVED]
**Performance Card (March 2026):**
| Metric | Value |
|---|---|
| Facebook Total | 60,873 |
| Instagram Total | 17,690 |
| Google Clicks | 348 |
| Social Stream Posts | 22 |
| Total Interactions | 78,911 |

**Stream-by-Stream Breakdown:**

| Stream | Posts | Locations | Total Interactions |
|---|---|---|---|
| EyeCarePro | 4 | 731 | 53,131 |
| AEG | 2 | 594 | 15,936 |
| Specialty: Dry Eye | 2 | 102 | 3,831 |
| Specialty: Vision Therapy | 2 | 36 | 2,143 |
| ProVision | 4 | 10 | 1,357 |
| Specialty: Sclerals | 1 | 75 | 1,291 |
| 20/20 Image Eye Centers | 4 | 9 | 89 |
| Glemaud | 1 | 44 | 666 |
| Specialty: Sports Vision | 2 | 28 | 467 |

### Social Connections (/a/social-connections) [OBSERVED]
**Connected Accounts:**
| Platform | Count | Percentage |
|---|---|---|
| Google Business | 2,120 | 73% |
| Facebook (Gsp) | 1,308 | 45% |
| Instagram (Biz) | 575 | 20% |

**Alerts:**
| Metric | Count |
|---|---|
| Broken Google | 101 |
| Available Google | 148 |
| No Google Business | 535 |
| Broken Facebook | 125 |
| Available Facebook | 131 |
| No Facebook | 1,340 |
| Broken Instagram | 0 |
| No Instagram | 2,329 |

**Total Platform Coverage:** 2,088 Practices, 2,904 Locations

## Practice-Level View [OBSERVED]
**URL:** /u/{id}/marketing/social/{locationId}

**What the practice sees:**
1. "Social Stream" page title with back arrow
2. Month navigator with arrows
3. Filter checkboxes: Social Stream Posts, Campaign Posts - Facebook, Campaign Posts - Instagram, Campaign Posts - GMB
4. CONNECT INSTAGRAM button (if not connected)
5. Facebook Insights sidebar: Likes, Comments, Shares, Impressions
6. Instagram Insights sidebar
7. Calendar grid (Sun–Sat) with post thumbnails, titles, times, color-coded borders (teal = Social Stream, blue = Campaign)

## Content Themes Observed (March 2026) [OBSERVED]
- Seasonal Allergies (main stream)
- Save Your Vision Month (main stream)
- New Season New Glasses (main stream)
- UV Protection (main stream)
- Dry Eye (specialty stream)
- Vision Therapy (specialty stream)
- Sports Vision (specialty stream)

## What Makes Social Posts Different

1. **Content included, not just the tool:** Pre-curated, professionally designed posts — not a blank canvas
2. **3-channel delivery:** Facebook + Instagram + Google Business Profile simultaneously
3. **Platform-optimized images:** Separate landscape (FB/Google) and square (IG) images per post
4. **Eye care-specific content:** 9 specialized streams covering general + clinical specialties
5. **Stream-based architecture:** Subscribe to content channels, not individual posts
6. **Zero ongoing effort:** Connect once, content flows forever
7. **Network scale:** One post reaches 731+ locations — enabling professional content at a fraction of individual cost
8. **Unified calendar:** Social Stream + Campaign social posts on one view
9. **Connection health monitoring:** Admin dashboard tracks broken/missing connections proactively
10. **Complements the stack:** Works alongside One-Click Campaigns (email + landing pages), Google Reviews, Directory Listings as part of the full marketing suite

## Best Use Case
Use Social Posts when you want a professional, consistent social media presence without creating content yourself. For multi-channel marketing campaigns with email and landing pages, use One-Click Campaigns. For recall and reminder automation, use Recalls & Reminders. For online reputation management, use Google Reviews.
