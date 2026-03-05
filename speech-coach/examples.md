# Speech Coach Examples

This document provides example transcripts and analyses to demonstrate the speech coaching workflow.

## Folder Structure

The speech coach organizes files as follows:

```
speech-coaching/
├── transcripts/                    # All transcript files
│   ├── standup-2026-03-05.txt
│   └── product-demo-2026-03-04.txt
├── analyses/                       # Generated analysis reports
│   ├── alex-2026-03-05.md
│   └── carlos-2026-03-04.md
└── speech-progress-{speaker}.md    # Progress tracker at root
```

---

## Example 1: Team Meeting Transcript

### Input: transcripts/standup-2026-03-05.txt

```
meeting-standup-2026-03-05.txt

[10:00] Sarah: Good morning everyone. Let's get started with our standup. Alex, do you want to go first?

[10:01] Alex: Yeah, sure. So, um, yesterday I was working on the, uh, the authentication module. And basically I got the, like, the login flow working but I'm still, you know, dealing with some edge cases. Actually, the the token refresh is giving me some trouble. So today I'll— I mean, I'm planning to finish that and then move on to the password reset feature. No blockers really, just need to, um, figure out that token thing.

[10:02] Sarah: Thanks Alex. Any help needed on the token refresh?

[10:03] Alex: No, I think I've got it. I just need to, like, look at how we're handling the expiration. It's basically a timing issue I think.

[10:04] Sarah: Okay, sounds good. Maria, you're next.

[10:05] Maria: Sure. Yesterday I completed the dashboard redesign. The new charts are live in staging. Today I'm starting on the notification system. I have one blocker — I need API specs from the backend team for the notification endpoints.

[10:06] Sarah: Got it. I'll follow up with the backend team after this. Anyone else have updates?
```

### Output: analyses/alex-2026-03-05.md

```markdown
# Speech Coaching Analysis for Alex

**Date**: 2026-03-05
**Context**: Daily standup meeting
**Transcript**: `transcripts/standup-2026-03-05.txt`

---

## TL;DR

Alex communicates the essential information but uses frequent filler words (um, uh, like, basically) that reduce clarity. The main priority is reducing fillers during transitions and when explaining technical concepts.

---

## Overall Assessment

### Strengths
| Strength | Evidence |
|----------|----------|
| Covers all standup elements | Mentions yesterday's work, today's plan, and blockers |
| Self-aware | "I think I've got it" shows appropriate confidence calibration |
| Responsive to questions | Directly answers Sarah's follow-up |

### Areas for Improvement
| Area | Priority | Impact |
|------|----------|--------|
| Filler word frequency | High | Reduces perceived confidence and clarity |
| Sentence restarts | Medium | Interrupts flow of information |
| Hedging language | Low | "I think", "basically" soften statements unnecessarily |

---

## Detailed Analysis

### 1. Filler Words

**Pattern Identified**: High frequency of fillers, especially during transitions and when explaining technical details.

**Examples from your speech**:
> "So, um, yesterday I was working on the, uh, the authentication module"
> "I just need to, like, look at how we're handling the expiration"

**Why This Happens**: Fillers often appear when we're thinking ahead to the next point while still speaking. Technical explanations trigger more fillers because we're translating complex thoughts into words.

**Improvement Strategy**:
- Pause silently instead of filling with "um" or "uh"
- Prepare your standup update mentally before speaking
- Practice the "pause and breathe" technique: when you feel a filler coming, take a brief breath instead

### 2. Sentence Restarts

**Pattern Identified**: Starting sentences, then restarting with different phrasing.

**Examples from your speech**:
> "So today I'll— I mean, I'm planning to finish that"
> "the the token refresh"

**Why This Happens**: Your brain is processing faster than your speech, causing mid-sentence corrections.

**Improvement Strategy**:
- Slow down slightly at the start of sentences
- It's okay to pause before starting a new thought
- If you restart, commit to the new direction without calling attention to it

### 3. Hedging Language

**Pattern Identified**: Softening statements with qualifiers that reduce impact.

**Examples from your speech**:
> "It's basically a timing issue I think"
> "No blockers really"

**Why This Happens**: Hedging feels safer, especially when discussing technical problems we haven't fully solved.

**Improvement Strategy**:
- Replace "I think" with direct statements when you're reasonably confident
- Save hedging for genuine uncertainty
- "It's a timing issue" is stronger than "It's basically a timing issue I think"

---

## Action Items for Next Time

- [ ] Prepare standup update in your head before speaking (30 seconds)
- [ ] Practice replacing "um/uh" with silent pauses
- [ ] Remove one hedge word per update ("basically", "really", "I think")

---

## Quick Reference Card

```
┌────────────────────────────────────────────────┐
│           ALEX'S SPEAKING CHECKLIST            │
├────────────────────────────────────────────────┤
│ □ Pause instead of saying "um" or "uh"         │
│ □ Commit to sentences — no restarts            │
│ □ State technical issues directly              │
└────────────────────────────────────────────────┘
```
```

### Output: speech-progress-alex.md (at root)

```markdown
# Speech Progress Tracker: Alex

**Native Language**: English

## Analysis History

### 2026-03-05 - Daily Standup
- **Transcript**: `transcripts/standup-2026-03-05.txt`
- **Analysis**: `analyses/alex-2026-03-05.md`
- **Key Metrics**:
  - Filler word rate: 8 per minute
  - Incomplete sentences: 2
  - Structure score: 3/5
- **Top Strengths**: Covers all standup elements, responsive to questions
- **Focus Areas**: Filler words, sentence restarts, hedging
- **Action Items**: Prepare updates beforehand, pause instead of filling, reduce hedges

---

## Trend Summary

| Date | Filler Rate | Completion | Structure | Overall |
|------|-------------|------------|-----------|---------|
| 2026-03-05 | 8/min | 85% | 3/5 | 3/5 |

---

## Recommended Focus for Next Session
1. Filler word reduction — aim for <5 per minute
```

---

## Example 2: Presentation Transcript (Non-Native Speaker)

### Input: transcripts/product-demo-2026-03-04.txt

```
product-demo-2026-03-04.txt

[00:00] Carlos: Hello everyone. Thank you for joining this demo. Today I will show you, eh, three main features of our new platform.

[00:15] Carlos: First, the dashboard. So, the dashboard gives you a complete view of your metrics. You can see here the, how do you say, the real-time data coming in. This is very important for monitoring.

[00:45] Carlos: Second feature is the alerting system. When something goes wrong, the system will notify you immediately. You can configure the thresholds here. For example, if CPU goes above 80 percent, you receive an alert.

[01:15] Carlos: And third, the reporting. You can generate reports automatically. Daily, weekly, monthly — whatever you need. The reports include all the metrics and you can export to PDF or Excel.

[01:45] Carlos: So, to summarize: dashboard for monitoring, alerts for problems, reports for analysis. Any questions?
```

### Output: analyses/carlos-2026-03-04.md

```markdown
# Speech Coaching Analysis for Carlos

**Date**: 2026-03-04
**Context**: Product demo presentation
**Transcript**: `transcripts/product-demo-2026-03-04.txt`
**Native Language**: Spanish

---

## TL;DR

Carlos delivers a well-structured presentation with clear signposting. Minor filler usage ("eh", "so") is within acceptable range for presentations. The structure is excellent — focus on maintaining this quality while slightly reducing transition fillers.

---

## Overall Assessment

### Strengths
| Strength | Evidence |
|----------|----------|
| Excellent structure | "Today I will show you three main features", "First... Second... Third..." |
| Clear signposting | "To summarize: dashboard for monitoring, alerts for problems, reports for analysis" |
| Appropriate pacing | Each feature gets dedicated time with examples |
| Invites engagement | "Any questions?" at the end |

### Areas for Improvement
| Area | Priority | Impact |
|------|----------|--------|
| Transition fillers | Low | Minor "so" usage at transitions |
| Word retrieval pauses | Low | "how do you say" — normal for bilingual speakers |

---

## Detailed Analysis

### 1. Structure (Strength)

**Pattern Identified**: Textbook presentation structure with clear roadmap and signposts.

**Examples from your speech**:
> "Today I will show you three main features"
> "First, the dashboard... Second feature is... And third, the reporting"
> "To summarize: dashboard for monitoring, alerts for problems, reports for analysis"

**Why This Works**: Audiences can follow along easily when they know what's coming. Your numbered structure creates mental "hooks" for retention.

**Keep Doing**: This structure is excellent. Continue using numbered lists and summaries.

### 2. Transition Fillers

**Pattern Identified**: "So" appears at the start of new sections.

**Examples from your speech**:
> "So, the dashboard gives you..."
> "So, to summarize..."

**Why This Happens**: "So" is a natural transition word, especially common when moving between prepared points. In Spanish, "pues" or "entonces" serve similar functions.

**Refinement Strategy**:
- This is minor and doesn't impede understanding
- If you want to polish further, try starting sections directly: "The dashboard gives you..." instead of "So, the dashboard..."
- Alternatively, use varied transitions: "Now let's look at...", "Moving to..."

### 3. Word Retrieval (Normal Pattern)

**Pattern Identified**: Brief pause with "how do you say" while finding the right term.

**Examples from your speech**:
> "You can see here the, how do you say, the real-time data"

**Why This Happens**: This is completely normal for bilingual speakers. Your brain is selecting from two language systems, which occasionally causes brief retrieval delays.

**Note**: This does NOT need to be "fixed." It's a natural part of bilingual speech. If you want to reduce it:
- Prepare key technical terms in advance
- It's fine to pause silently instead of saying "how do you say"

---

## Action Items for Next Time

- [ ] Continue using numbered structure — it's working well
- [ ] Optional: Vary transition phrases ("Now...", "Next...", "Moving on...")
- [ ] Pre-review technical terms you'll need in English

---

## Quick Reference Card

```
┌────────────────────────────────────────────────┐
│          CARLOS'S SPEAKING CHECKLIST           │
├────────────────────────────────────────────────┤
│ ✓ Use numbered structure (keep doing this!)   │
│ ✓ Summarize at the end (keep doing this!)     │
│ □ Vary transition words for polish            │
└────────────────────────────────────────────────┘
```
```

---

## Example 3: Progress Comparison (Multiple Sessions)

### speech-progress-alex.md (at root, with history)

```markdown
# Speech Progress Tracker: Alex

**Native Language**: English

## Analysis History

### 2026-03-05 - Daily Standup
- **Transcript**: `transcripts/standup-2026-03-05.txt`
- **Analysis**: `analyses/alex-2026-03-05.md`
- **Key Metrics**:
  - Filler word rate: 8 per minute
  - Incomplete sentences: 2
  - Structure score: 3/5
- **Top Strengths**: Covers all standup elements, responsive
- **Focus Areas**: Filler words, sentence restarts
- **Action Items**: Prepare updates beforehand, pause instead of filling

### 2026-02-26 - Sprint Review
- **Transcript**: `transcripts/sprint-review-2026-02-26.txt`
- **Analysis**: `analyses/alex-2026-02-26.md`
- **Key Metrics**:
  - Filler word rate: 12 per minute
  - Incomplete sentences: 5
  - Structure score: 2/5
- **Top Strengths**: Technical depth, honest about challenges
- **Focus Areas**: Filler words, structure, sentence completion
- **Action Items**: Use signposts, prepare talking points

### 2026-02-19 - Team Meeting
- **Transcript**: `transcripts/team-meeting-2026-02-19.txt`
- **Analysis**: `analyses/alex-2026-02-19.md`
- **Key Metrics**:
  - Filler word rate: 15 per minute
  - Incomplete sentences: 7
  - Structure score: 2/5
- **Top Strengths**: Engaged with questions
- **Focus Areas**: High filler rate, many restarts
- **Action Items**: Slow down, pause before speaking

---

## Trend Summary

| Date | Filler Rate | Completion | Structure | Overall |
|------|-------------|------------|-----------|---------|
| 2026-02-19 | 15/min | 70% | 2/5 | 2/5 |
| 2026-02-26 | 12/min | 78% | 2/5 | 2.5/5 |
| 2026-03-05 | 8/min | 85% | 3/5 | 3/5 |

---

## Recurring Patterns

### Persistent Strengths
- Engages well with questions and follow-ups
- Provides good technical detail
- Honest about blockers and challenges

### Persistent Challenges
- Filler words during transitions (improving)
- Sentence restarts when explaining technical concepts

---

## Recommended Focus for Next Session
1. Continue filler reduction — great progress from 15 to 8 per minute
2. Work on structure in longer-form speaking (sprint reviews)
3. Practice the "pause and commit" technique for sentence starts
```

---

## Metrics Reference

### Filler Word Benchmarks

| Context | Excellent | Good | Needs Work |
|---------|-----------|------|------------|
| Formal presentation | <3/min | 3-5/min | >5/min |
| Team meeting | <5/min | 5-8/min | >8/min |
| Casual discussion | <8/min | 8-12/min | >12/min |

### Structure Score Guide

| Score | Description |
|-------|-------------|
| 5 | Clear intro, logical flow, smooth transitions, strong conclusion |
| 4 | Good structure with minor jumps, uses signposts |
| 3 | Adequate structure, some topic jumping, few signposts |
| 2 | Disorganized, frequent topic changes, hard to follow |
| 1 | No discernible structure, stream of consciousness |

### Completion Rate Guide

| Rate | Assessment |
|------|------------|
| 90%+ | Excellent |
| 80-89% | Good |
| 70-79% | Needs attention |
| <70% | Priority focus area |

---

*These examples demonstrate the speech coaching analysis workflow. Actual analyses will be tailored to the specific transcript and speaker context.*
