---
name: schola-user-intent-taxonomy
description: Schola's 4-phase taxonomy for classifying student intent in social media comments and messages — codes 1.1–4.1 plus OTHER
metadata:
  type: concept
  sources:
    - source: manual
      path: default/1781059623238-AI Automation Project_Social Media Comment Taxonomy Classifier.pdf
---

# Concept: Schola User Intent Taxonomy

**Owner:** Schola product team  
**Current version:** V3 (V4 in future roadmap)  
**Used by:** [[social-media-comment-classifier-pipeline]], Claude classification prompt  

## Purpose

A structured coding scheme for classifying the underlying intent of student-authored text (comments, messages, feedback) across career exploration, pathway planning, execution, and emotional support phases. Applied by Claude as part of the [[social-media-comment-classifier-pipeline]].

## Taxonomy Codes

### Phase 1: Self & Career Exploration

| Code | Description |
|------|-------------|
| 1.1 | No clear direction — wants general career ideas or possibilities |
| 1.2 | No clear direction — wants to understand themselves better (interests, strengths, personality) |
| 1.3 | Wants tailored career suggestions based on interests or preferences |
| 1.4 | Evaluating whether career suggestions / job info are accurate, relevant, or "fit them" |
| 1.5 | Wants factual information about a job, field/industry, or role |
| 1.6 | Confirms or affirms a chosen career goal |

### Phase 2: Pathway Planning

| Code | Description |
|------|-------------|
| 2.1 | No clear direction — wants general pathway options or next steps |
| 2.2 | Wants tailored pathway suggestions (courses, training, skills, certifications) based on career goals or constraints |
| 2.3 | Wants factual info (duration, requirements, cost) about a specific pathway |
| 2.4 | Evaluating which pathways suit them |
| 2.5 | Confirms or affirms their pathway plan |

### Phase 3: Execution

| Code | Description |
|------|-------------|
| 3.1 | Looking for actual job vacancies or execution steps to get a job |

### Phase 4: Emotional Support

| Code | Description |
|------|-------------|
| 4.1 | Needs encouragement, reassurance, or confidence-building in career exploration & pathway planning |

### Special Code

| Code | Description |
|------|-------------|
| OTHER | Does not fit clearly within Phase 1–4; includes scholarship discussions without career intent, platform feedback unrelated to career decisions, education topics outside the taxonomy |

## Classification Rules

1. **Primary tag required** — every item gets exactly one primary code representing dominant intent.
2. **Secondary tag optional** — only if a clearly second distinct Phase 1–4 intent is present.
3. **Intent is bidirectional** — tag both desire ("how do I find a job?") and accomplishment ("I found a job!") with the same code (e.g., 3.1).
4. **Scholarships rule** — if primarily about scholarships → OTHER as primary. Exception: use Phase 1–4 as primary if dominant, scholarships as secondary if mappable.
5. **Surface intent vs. underlying intent** — even feedback/UX suggestions/testimonials are tagged by their underlying Phase 1–4 intent.

## Confidence Levels

| Level | Criterion |
|-------|-----------|
| HIGH | Category is explicit or strongly implied by text |
| MEDIUM | Reasonable inference required |
| LOW | Significant ambiguity; label is a best guess among several plausible options |

## Versioning

The product team updates the prompt when taxonomy codes change (e.g., V3 → V4). Edge cases and misclassifications from the review loop feed back into prompt refinement.
