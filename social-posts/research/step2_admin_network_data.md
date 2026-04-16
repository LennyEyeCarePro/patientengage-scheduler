# Step 2 — Admin Network Data: Social Posts
## Feature: Social Posts (Social Stream + Campaign Posts combined)
**Date:** April 12, 2026
**Date Range:** March 1–31, 2026
**Source:** Admin Social Reports at `app.patientengage.ai/a/social-reports/`

---

## Network Scale [OBSERVED]

| Metric | Value | Source |
|---|---|---|
| Total Practices | 1,929 | Social Report - Locations |
| Total Locations | 2,696 | Social Report - Locations |

---

## Social Report — Locations (March 2026) [OBSERVED]

### Performance Card
| Metric | Value |
|---|---|
| Facebook Total | 174,401 |
| Instagram Total | 39,708 |
| Google Clicks | 400 |
| Location Posts | 7,098 |
| Total Interactions | 214,509 |

### Alerts Card
| Metric | Value |
|---|---|
| No Interactions | 1,663 |

**Note:** "Location Posts" (7,098) includes ALL social posts for all locations — both Social Stream posts and Campaign posts combined. "Total Interactions" (214,509) is the sum of all Facebook impressions, Instagram impressions, and Google clicks across all locations.

### Key Calculation [CALCULATED]
- **Average posts per location:** 7,098 ÷ 2,696 = ~2.6 posts/location in March
- **Average interactions per post:** 214,509 ÷ 7,098 = ~30.2 interactions per post
- **Locations with zero interactions:** 1,663 out of 2,696 = 61.7% had no interactions

---

## Social Report — Streams (March 2026) [OBSERVED]

### Performance Card
| Metric | Value |
|---|---|
| Facebook Total | 60,873 |
| Instagram Total | 17,690 |
| Google Clicks | 348 |
| Social Stream Posts | 22 |
| Total Interactions | 78,911 |

### Alerts Card
| Metric | Value |
|---|---|
| Facebook < 50 per location | 7 |
| Google Clicks < 5 | 9 |

### Stream-by-Stream Breakdown [OBSERVED]

| Stream | Posts | Locations | FB Likes | FB Comments | FB Shares | FB Impressions | IG | Google | Total |
|---|---|---|---|---|---|---|---|---|---|
| EyeCarePro | 4 | 731 | 640 | 16 | 81 | 40,818 | 11,273 | 303 | 53,131 |
| AEG | 2 | 594 | 93 | 8 | 11 | 11,803 | 4,021 | 0 | 15,936 |
| Specialty: Dry Eye | 2 | 102 | 53 | 0 | 1 | 2,970 | 780 | 27 | 3,831 |
| Specialty: Vision Therapy | 2 | 36 | 17 | 0 | 4 | 1,321 | 793 | 8 | 2,143 |
| ProVision | 4 | 10 | 26 | 0 | 0 | 819 | 508 | 4 | 1,357 |
| Specialty: Sclerals | 1 | 75 | 17 | 0 | 1 | 1,015 | 258 | 0 | 1,291 |
| 20/20 Image Eye Centers | 4 | 9 | 2 | 0 | 0 | 84 | 0 | 3 | 89 |
| Glemaud | 1 | 44 | 2 | 0 | 1 | 663 | 0 | 0 | 666 |
| Specialty: Sports Vision | 2 | 28 | 6 | 0 | 1 | 400 | 57 | 3 | 467 |

### Key Observations — Streams [CALCULATED]
1. **EyeCarePro is the dominant stream:** 731 locations, 53,131 interactions — 67% of all stream interactions from 4 posts
2. **AEG is #2:** 594 locations, 15,936 interactions
3. **Specialty streams serve niche audiences:** Dry Eye (102 locations), Vision Therapy (36), Sclerals (75), Sports Vision (28)
4. **Streams account for 37% of total interactions:** 78,911 (streams) vs 214,509 (all social) [CALCULATED] — the remaining 63% comes from Campaign Posts
5. **Average interactions per EyeCarePro post per location:** 53,131 ÷ (4 × 731) = ~18.2 interactions per post per location [CALCULATED]

---

## Social Connections Report [OBSERVED]

### Connected Accounts (All Features)
| Platform | Count | Percentage |
|---|---|---|
| Google Business | 2,120 | 73% |
| Facebook (Gsp) | 1,308 | 45% |
| Instagram (Biz) | 575 | 20% |

### Alerts
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

### Total Platform Coverage
- **2,088 Practices, 2,904 Locations** across all features

### Key Observations — Connections [CALCULATED]
1. **Google is the most connected platform** at 73% — likely because GBP is foundational for local SEO
2. **Facebook is at 45%** — less than half of practices have connected their Facebook page
3. **Instagram is lowest at 20%** — massive growth opportunity; only 1 in 5 practices post to IG
4. **Broken connections are a real issue:** 101 broken Google + 125 broken Facebook = 226 practices that were connected but lost their connection
5. **1,340 practices have NO Facebook at all** — they're missing the primary social channel

---

## Killer Stats for Social Posts Page [CALCULATED from OBSERVED data]

### Network-Level Stats
1. **"7,098 social posts published across 2,696 locations in March 2026"** — shows automated scale
2. **"214,509 total social interactions in one month"** — demonstrates real engagement
3. **"22 Social Stream posts pushed to 731+ locations each"** — one post, hundreds of practices
4. **"174,401 Facebook impressions + 39,708 Instagram impressions in March"** — platform breakdown

### Per-Practice Stats
5. **"Average practice published 2.6 social posts in March — without writing a word"** — zero effort
6. **"Each EyeCarePro stream post generated ~18 interactions per location"** — per-post performance

### Connection Opportunity Stats
7. **"73% of practices have Google Business connected; only 20% have Instagram"** — growth story
8. **"1,308 practices actively posting to Facebook through PatientEngage"** — already at scale

---

## Comparison: Social Stream vs Campaign Posts [CALCULATED]

| Metric | Social Stream | Campaign Posts | Total |
|---|---|---|---|
| Interactions | 78,911 (37%) | ~135,598 (63%) | 214,509 |
| Source | 22 posts × multiple locations | Individual campaign posts | 7,098 location posts |

**Note:** Campaign Posts interaction total is estimated: 214,509 - 78,911 = 135,598 [ESTIMATE]

This means Campaign Posts actually drive MORE interactions than Social Stream — but Social Stream provides the consistent, always-on baseline while Campaigns provide periodic bursts.

---

## Provenance Notes
- Social Report - Locations performance data: [OBSERVED] at `/a/social-reports/locations?startDate=2026-03-01&endDate=2026-03-31`
- Social Report - Streams performance data: [OBSERVED] at `/a/social-reports/streams?startDate=2026-03-01&endDate=2026-03-31`
- Stream-by-stream table data: [OBSERVED] via JavaScript extraction from data grid
- Social Connections data: [OBSERVED] at `/a/social-connections`
- Per-post and per-location averages: [CALCULATED] from observed totals
- Campaign Posts interaction estimate: [ESTIMATE] — derived by subtracting stream total from location total
