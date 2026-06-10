---
name: social-media-comment-classifier-pipeline
description: End-to-end 5-step pipeline for extracting, translating, classifying, reporting, and reviewing Schola's social media comments using Claude and the Schola User Intent Taxonomy
metadata:
  type: concept
  sources:
    - source: manual
      path: default/1781059623238-AI Automation Project_Social Media Comment Taxonomy Classifier.pdf
---

# Concept: Social Media Comment Classifier Pipeline

**Operator:** [[schola]]  
**LLM:** Claude  
**Output store:** Google Sheets + Slack  
**Taxonomy:** [[schola-user-intent-taxonomy]]  

## Overview

A 5-step automated pipeline that pulls comments from Schola's social media posts, classifies each comment against the Schola User Intent Taxonomy using Claude, delivers structured outputs, and maintains quality through a human-in-the-loop review cycle.

---

## Step 1: Automated Data Extraction & Cleaning

**Goal:** Pull raw comments from social media into a Google Sheet.

**APIs:**
- Instagram Graph API (Phase 1)
- TikTok Research API (Phase 2; Threads also Phase 2 subject to access)

**Raw fields collected per comment:**
- Post URL / ID
- Platform
- Timestamp
- Comment Text
- Username (optional / anonymised)

**Translation step:** Non-English comments (Bahasa Malaysia, Chinese) are translated to English and stored in a new column `Comment Text (EN)` immediately to the right of the original.

**Final Tab 1 schema:**
```
Post URL/ID | Platform | Timestamp | Comment Text | Comment Text (EN)
```
Rows grouped by campaign.

**Operational modes:**
- Specific time frame: Aug 2024 to present
- Frequency-based: weekly
- Campaign-based: target post list (12 Instagram Reels identified)

**Open questions:** Scheduled vs. manual trigger; campaign-level filtering; exclude own-account comments.

---

## Step 2: Analysis by Claude

**Goal:** Classify each comment against the taxonomy.

**Input to LLM per comment:**
- Comment Text (EN)
- Full [[schola-user-intent-taxonomy]] embedded in prompt
- Structured prompt requesting: Primary Intent code, Secondary Intent code (if any), Confidence level, reasoning note

**Classification output schema (Tab 2):**
```
Post URL/ID | Platform | Comment Text (EN) | Primary Intent (Code) | Secondary Intent (Code) | Confidence | Notes
```
Rows grouped by campaign.

**Example classifications:**
- "Once you succeed later, everyone will go quiet." → PRIMARY: OTHER, CONFIDENCE: MEDIUM (career-related but intent unclear)
- "Is there a proper guide for filling in UPU?" → PRIMARY: 2.3, CONFIDENCE: HIGH (request for pathway factual info)

---

## Step 3: Output Delivery

Results written to a **Google Sheet** with two tabs:
- **Tab 1:** Raw data pull & translation (Step 1 output)
- **Tab 2:** Classified data (Step 2 output)

---

## Step 4: Reporting

After each cycle, a **Slack summary report** is sent to a dedicated channel covering:
- Run date
- Number of comments analysed
- Number successfully categorised
- Number of outliers (labelled "OTHER")

---

## Step 5: Review Loop

**Current process (manual):**
1. Product team samples a subset of classifications each cycle
2. Edge cases and misclassifications feed back into prompt refinement
3. Taxonomy version updates (V3 → V4) trigger prompt updates

**Open question:** Best practices and automation extent for this feedback/improvement loop.

---

## Claude System Prompt (Verbatim from Brief)

**Role framing:** Expert Qualitative Data Analyst specialising in career and pathway planning for students. Classifies qualitative text into the Schola User Intent Taxonomy with high precision and minimal over-interpretation.

**Language handling:** Data from Malaysian students — mix of English, Malay, "Manglish." Categorise based on underlying meaning without translating first.

**Output format:** Markdown table with columns:
`Original Text | Primary Intent | Secondary Intent | Confidence | Notes/Reasoning`
