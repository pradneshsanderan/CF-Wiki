---
name: schola-social-media-comment-taxonomy-classifier
description: Project brief for Schola's AI-powered social media comment taxonomy classifier — covers pipeline design, Claude classification prompt, taxonomy codes, and review loop
metadata:
  type: source
  sources:
    - source: manual
      path: default/1781059623238-AI Automation Project_Social Media Comment Taxonomy Classifier.pdf
---

# Source: Social Media Comment Taxonomy Classifier (Project Brief)

**Origin:** PDF project brief, manually staged  
**Organisation:** Schola (schola.my)  
**Document type:** AI Automation Project Brief  

## Summary

A guidance and collaborative session document for the Schola product team to learn how to set up and self-manage an AI-powered pipeline that extracts social media comments, classifies them against Schola's User Intent Taxonomy using Claude, and delivers structured reports.

## Document Sections

1. **Project Brief** — scope overview and 5-step pipeline
2. **Claude Prompt: Analysis of Qualitative Data** — the full taxonomy categorisation system prompt
3. **Informatic Items** — operational data: target post URLs, platform phases, taxonomy table, confidence thresholds

## Key Facts Extracted

- Client/operator: Schola team (product team owns review loop)
- Platforms: Instagram (Phase 1), TikTok + Threads (Phase 2)
- LLM used for classification: Claude
- Output destination: Google Sheet (2 tabs) + Slack summary report
- Data language: English, Bahasa Malaysia, Chinese → translated to English before storage
- Taxonomy version referenced: current (V3 implied; V4 mentioned as future)
- Historical pull window: Aug 2024 to present
- Scheduled cadence: weekly

## Open Questions Captured

- Can extraction run on a set frequency AND be triggered manually?
- Can extraction filter to posts belonging to a specific campaign?
- Can Schola's own account comments be excluded?
- Best practices for the feedback/improvement loop, and automation extent?

## Credentials Note

The source document contains social media account credentials. These have been **intentionally omitted** from all wiki pages for security reasons.
