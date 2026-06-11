---
name: amplitude-user-journeys-prev30days
description: Amplitude export of user session journeys over the previous 30 days (data spans 2023-10-28 to 2026-06-16, concentrated in 2026-W21–W22)
metadata:
  type: source
sources:
  - source: manual
    path: default/1781148074683-user_journeys-Amplitude-prev30days.csv
---

# Amplitude User Journeys — Previous 30 Days

**File:** `1781148074683-user_journeys-Amplitude-prev30days.csv`
**Export date context:** 2026-06-11 (query window: prev 30 days)
**Rows:** 15,301 sessions
**Actual date range in data:** 2023-10-28 – 2026-06-16 (bulk in 2026-W21 and W22)

## Schema

| Column | Description |
|---|---|
| `amplitude_id` | Amplitude anonymous device ID |
| `user_id` | Platform user ID (blank for unauthenticated) |
| `session_id` | Unique session identifier |
| `start_time` / `end_time` | Session boundaries (UTC) |
| `steps` | Number of events in the session |
| `path` | JSON array of ordered event names |
| `affinity_result` | RIASEC 1-3 letter code from career affinity quiz |
| `primary_trait` / `secondary_trait` | Personality archetype labels in Malay |
| `custom_age` | Self-reported age or range |
| `custom_gender`, `custom_education_level`, `custom_future_plan` | Profile attributes |
| `custom_user_role` | student / parent / teacher / other |
| `custom_target_group` | Schola targeting segment |
| `utm_source`, `utm_campaign`, `initial_utm_source` | Attribution fields |
| `referring_domain`, `initial_referring_domain` | Traffic source domains |
| `visit_counter` | Cumulative visit count for the user |
| `login_type` | Guest / Google / Email / Facebook |
| `preferred_language` | `ms` (Malay) or blank |
| `read_guides_count`, `downloaded_resources_count` | Engagement depth metrics |
| `answered_job_tests_count`, `bookmarked_jobs_guides_count` | Quiz and save engagement |
| `leads_ID` | CRM lead identifier |

## Data Quality Notes

- 86.8% of rows have blank `affinity_result` — most sessions do not reach quiz completion.
- `custom_age` is inconsistently formatted: free-text integers (e.g. "17"), range strings ("18 to 25"), and "below 18".
- `read_guides_count`, `answered_job_tests_count` are blank for ~98% of rows (only populated for logged-in users).
- `visit_counter` is blank for 78 rows.
- Several near-identical session records appear with dates outside the 30-day window (2023, 2024, 2025), suggesting older sessions re-surfaced by Amplitude's query or test accounts.
