---
name: speech-coach
description: Analyze speech transcripts to provide communication coaching, identify speaking patterns, track progress over time. Use when the user wants feedback on a presentation, meeting transcript, talk, or speech quality improvement.
---

# Speech Coach

Analyze transcripts of meetings, presentations, or talks to provide actionable communication coaching.

## Folder Structure

The speech coach uses a dedicated folder structure to organize transcripts, analyses, and progress tracking. When the user provides a base directory (or uses the current workspace), create this structure:

```
{base-directory}/
├── transcripts/                    # All transcript files go here
│   ├── meeting-2026-03-05.txt
│   ├── presentation-2026-03-04.txt
│   └── ...
├── analyses/                       # Generated analysis reports
│   ├── {speaker}-{date}.md
│   └── ...
└── speech-progress-{speaker}.md    # Progress tracker at root (one per speaker)
```

### Folder Rules

1. **transcripts/**: Store all uploaded or provided transcript files here
   - When user provides a transcript, copy or move it to this folder
   - Naming convention: `{context}-{date}.txt` (e.g., `standup-2026-03-05.txt`)

2. **analyses/**: Store all generated coaching analysis reports here
   - Naming convention: `{speaker-name}-{date}.md` (e.g., `alex-2026-03-05.md`)
   - Each analysis links back to its source transcript

3. **Progress files at root**: One progress tracker per speaker at the base directory
   - Naming convention: `speech-progress-{speaker-name}.md`
   - Contains cumulative history across all analyses for that speaker

### Setup

When starting a new speech coaching session:
1. Ask the user for the base directory (default: current workspace or a `speech-coaching/` subfolder)
2. Create the folder structure if it doesn't exist
3. Check for existing progress files at the root to load history

## Workflow

### Step 1: Identify the Speaker and Context

If the transcript contains multiple speakers, ask the user which person to analyze and gather context:

```
Use AskQuestion tool with multiple questions:

1. "Which speaker would you like me to analyze?"
   - Options: [list of speakers found in transcript]

2. "What is the speaker's native language?"
   - Options: ["English", "Spanish", "Portuguese", "French", "German", "Italian", "Other (will ask)", "Unknown/Prefer not to say"]
```

If the user selects "Other", ask them to specify in a follow-up.

If only one speaker or user specifies upfront, still ask about native language unless already known from a previous progress file.

### Step 2: Read the Transcript

Read the provided transcript file. Extract all speech from the target speaker.

### Step 3: Load Progress History (if exists)

Check for existing progress file at the root of the speech coaching folder:
- Look for `speech-progress-{speaker-name}.md` in the base directory
- If found, read previous analyses to compare progress
- If native language was recorded previously, use that instead of asking again

### Step 4: Analyze Speech Patterns

Evaluate these dimensions:

| Category | What to Look For |
|----------|------------------|
| **Filler Words** | "um", "uh", "like", "you know", "okay", "so", "basically", "actually" |
| **Sentence Completion** | Interrupted thoughts, incomplete sentences, restarts |
| **Structure** | Linear flow vs jumping between topics, use of signposts |
| **Repetition** | Word/phrase repetition, stuttering patterns |
| **Clarity** | Vague vs precise language, jargon overuse |
| **Engagement** | Questions to audience, acknowledgments, name usage |
| **Pacing** | Rush indicators, appropriate pauses |

### Step 5: Generate Analysis Report

Create a markdown document with this structure:

```markdown
# Speech Coaching Analysis for {Speaker Name}

**Date**: {date}
**Context**: {meeting/presentation type}
**Transcript**: {filename}

---

## TL;DR

{2-3 sentence summary of overall performance and top priorities}

---

## Overall Assessment

### Strengths
| Strength | Evidence |
|----------|----------|
| {strength} | "{quote from transcript}" |

### Areas for Improvement
| Area | Priority | Impact |
|------|----------|--------|
| {area} | High/Medium/Low | {why it matters} |

---

## Detailed Analysis

### 1. {First Priority Area}

**Pattern Identified**: {description}

**Examples from your speech**:
> "{direct quote}"

**Why This Happens**: {explanation}

**Improvement Strategy**:
{actionable advice}

{Repeat for each area}

---

## Action Items for Next Time

- [ ] {Specific, actionable item 1}
- [ ] {Specific, actionable item 2}
- [ ] {Specific, actionable item 3}

---

## Progress Tracking

{If previous analysis exists, show comparison}

### Metrics Comparison
| Metric | Previous | Current | Change |
|--------|----------|---------|--------|
| Filler words per minute | X | Y | +/-% |
| Incomplete sentences | X | Y | +/-% |

### Improvements Noted
- {What got better}

### Still Working On
- {What needs continued focus}

---

## Quick Reference Card

\`\`\`
┌────────────────────────────────────────────────┐
│        {SPEAKER}'S SPEAKING CHECKLIST          │
├────────────────────────────────────────────────┤
│ □ {Top priority 1}                             │
│ □ {Top priority 2}                             │
│ □ {Top priority 3}                             │
└────────────────────────────────────────────────┘
\`\`\`
```

### Step 6: Update Progress File

Create or update `speech-progress-{speaker-name}.md` at the root of the base directory:

```markdown
# Speech Progress Tracker: {Speaker Name}

**Native Language**: {language from Step 1}

## Analysis History

### {Date} - {Context}
- **Transcript**: `transcripts/{filename}`
- **Analysis**: `analyses/{speaker-name}-{date}.md`
- **Key Metrics**:
  - Filler word rate: X per minute
  - Incomplete sentences: X
  - Structure score: X/5
- **Top Strengths**: {list}
- **Focus Areas**: {list}
- **Action Items**: {list}

{Append new entries, keep history}

---

## Trend Summary

| Date | Filler Rate | Completion | Structure | Overall |
|------|-------------|------------|-----------|---------|
| {date} | X/min | X% | X/5 | X/5 |

---

## Recurring Patterns

### Persistent Strengths
- {patterns that appear consistently positive}

### Persistent Challenges
- {patterns that need ongoing work}

---

## Recommended Focus for Next Session
1. {Based on trends, what to prioritize}
```

### Step 7: Save Output

Save files to the appropriate locations in the folder structure:
- **Transcript**: Ensure it's in `transcripts/` folder (copy if provided from elsewhere)
- **Analysis**: Save to `analyses/{speaker-name}-{date}.md`
- **Progress**: Create or update `speech-progress-{speaker-name}.md` at the root

## Analysis Guidelines

### Counting Metrics

- **Filler word rate**: Count fillers, estimate speaking time from transcript length
- **Completion rate**: (Complete sentences / Total sentence attempts) × 100
- **Structure score**: 1-5 based on logical flow and signposting

### Prioritization

Rank issues by:
1. **Frequency**: How often does it occur?
2. **Impact**: How much does it affect comprehension?
3. **Fixability**: Can it be improved with practice?

### Tone

- Be constructive, not critical
- Acknowledge strengths before weaknesses
- Provide specific, actionable advice
- For non-native speakers, note that accents are fine—focus on clarity

### Context Awareness

Consider:
- Formal presentation vs casual meeting
- Technical vs general audience
- Native language background (use confirmed info from Step 1, not assumptions)
- Interactive discussion vs monologue

### Native Language Considerations

When the speaker's native language is known:
- Note common L1 transfer patterns specific to that language
- Frame these as normal, not errors
- Focus coaching on clarity and impact, not accent or minor grammar
- Do NOT assume native language from names or context—always confirm

## Example Interaction

User: "Analyze my speech from this transcript @meeting-transcript.txt"

Agent:
1. Read transcript
2. Identify speakers → Ask which one to analyze
3. Check for existing progress file
4. Analyze speech patterns
5. Generate coaching report
6. Update progress tracker
7. Present summary and save files
