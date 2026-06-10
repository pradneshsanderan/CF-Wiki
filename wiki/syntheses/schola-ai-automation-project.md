---
name: schola-ai-automation-project
description: Synthesis of Schola's AI automation project — social media comment taxonomy classification system; covers design decisions, open questions, and agent-retrieval context
metadata:
  type: synthesis
  sources:
    - source: manual
      path: default/1781059623238-AI Automation Project_Social Media Comment Taxonomy Classifier.pdf
---

# Synthesis: Schola AI Automation Project

## What This Is

[[schola]] is building an automated pipeline to classify student-authored social media comments against their proprietary [[schola-user-intent-taxonomy]] using Claude as the classification engine. The brief documents both the full [[social-media-comment-classifier-pipeline]] design and the Claude system prompt used for classification.

## Why It Matters

Schola's core product helps Malaysian students with career and pathway planning. Social media comments are a high-signal qualitative data source for understanding what students actually need. Systematic classification enables:
- Trend analysis by intent phase across campaigns
- Surfacing outliers (OTHER-coded comments) that may indicate taxonomy gaps
- Product and content decisions grounded in student signal

## Architecture Summary

```
Instagram / TikTok APIs
        ↓
  Raw comment extraction
        ↓
  Auto-translation (BM/Chinese → EN)
        ↓
  Claude classification (taxonomy codes + confidence)
        ↓
  Google Sheet (Tab 1: raw | Tab 2: classified)
        ↓
  Slack cycle report
        ↓
  Human review loop → prompt refinement
```

## Design Decisions Noted in Brief

| Decision | Choice |
|----------|--------|
| LLM for classification | Claude |
| Translation timing | Post-extraction, pre-classification |
| Output medium | Google Sheets (2-tab) |
| Notification channel | Slack |
| Review process | Manual sampling by product team |
| Taxonomy versioning | Product team owns; prompt updated on version change |

## Open Questions (Unresolved in Brief)

1. **Scheduling** — can extraction be both scheduled and manually triggered?
2. **Campaign filtering** — can extraction scope be limited to specific campaign posts?
3. **Account exclusion** — can Schola's own account comments be filtered out?
4. **Feedback loop automation** — best practices and automation feasibility for the review/refinement cycle?

## Key Entities

- [[schola]] — operator and taxonomy owner
- [[schola-user-intent-taxonomy]] — 4-phase, 11-code classification scheme (+ OTHER)
- [[social-media-comment-classifier-pipeline]] — the full 5-step workflow

## Retrieval Notes

- The full taxonomy table (codes 1.1–4.1 + OTHER) is in [[schola-user-intent-taxonomy]]
- The verbatim Claude system prompt structure is in [[social-media-comment-classifier-pipeline]] Step 2
- Sample classified comments (UPU Results Release campaign) are in the source document, Step 3
- Credentials from the source document have been redacted and are not stored in this wiki
