---
name: user-demographics
description: User demographic profile from self-reported attributes in Amplitude session data
metadata:
  type: concept
sources:
  - source: manual
    path: default/1781148074683-user_journeys-Amplitude-prev30days.csv
---

# User Demographics

Profile data from 15,301 sessions. Most attributes are only populated for users who completed onboarding (~15% of sessions).

## Age Distribution (among profiled users)

| Age | Sessions |
|---|---|
| 17 | 1,213 |
| 18 | 737 |
| 16 | 542 |
| 15 | 311 |
| 18–25 (range) | 122 |
| 14 | 111 |
| below 18 (range) | 89 |
| 19 | 174 |
| 26–35 (range) | 70 |

Core demographic: **15–18 year olds** (secondary school students). Users below 18 account for the vast majority of profiled sessions.

## Language Preference

- **Malay (ms):** 5,836 sessions
- Not set: 9,465 sessions

The platform is Malay-first; absence of English preference data is expected.

## User Role

| Role | Count |
|---|---|
| Student | 5,004 |
| Other | 340 |
| Parent | 172 |
| Teacher | 55 |
| Not set | 9,730 |

## Education Level

Sparsely populated (only 276 rows set). Values seen: `True`, `False`, `SMK school` — suggests a boolean or multi-select field with inconsistent data capture.

## Future Plan (custom survey)

| Plan | Count |
|---|---|
| "study more lah, what else!" | 251 |
| "travel the world!" | 26 |
| "work on self-improvement!" | 15 |
| "start my own business!" | 3 |
| others | 2 |

Overwhelmingly academic future orientation among users who answered.

## Preferred Language for Platform Content

Malay (`ms`) is recorded for 38.1% of sessions; remainder have no preference set (likely defaults or anonymous).
