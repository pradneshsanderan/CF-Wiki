---
name: traffic-acquisition
description: Traffic source breakdown and UTM attribution patterns from Amplitude session data
metadata:
  type: concept
sources:
  - source: manual
    path: default/1781148074683-user_journeys-Amplitude-prev30days.csv
---

# Traffic Acquisition

Session-level attribution from Amplitude journey export (15,301 sessions, 2026-W21–W22 majority).

## Referring Domains (current session)

| Domain | Sessions |
|---|---|
| www.google.com | 7,609 |
| (direct / not set) | 5,355 |
| l.threads.com | 1,377 |
| www.tiktok.com | 234 |
| com.google.android.googlequicksearchbox | 179 |
| l.instagram.com | 179 |
| www.bing.com | 114 |
| www.google.com.my | 62 |
| malaysia.search.yahoo.com | 50 |
| m.facebook.com | 32 |

Google (organic + paid) dominates. Threads is the leading social referrer.

## UTM Sources (session-level)

| Source | Sessions |
|---|---|
| Duta (ambassador program) | 1,103 |
| threads | 372 |
| tiktok | 281 |
| instagram | 207 |
| ta1 | 59 |
| suk | 45 |
| jomstudy | 42 |
| kjmu | 18 |
| ig_text_post_permalink | 15 |

**Duta** is the largest tagged source — an ambassador/influencer referral program.

## UTM Campaigns

Most sessions lack campaign tagging (15,213 blank). Tagged campaigns include:
- `ss3` (51 sessions) — likely "social media sprint 3"
- `upsidr`, `tc1`, `upsisl`, `trpapr1` — partnership or institution codes
- `Students+UPU+Application` (3) — UPU is Malaysia's university placement system

## Login Type

| Type | Sessions |
|---|---|
| Not logged in | 14,686 (96.0%) |
| Google | 381 (2.5%) |
| Guest | 142 (0.9%) |
| Email | 91 (0.6%) |
| Facebook | 1 |

Platform is predominantly used anonymously. Google SSO is the dominant auth method among logged-in users.
