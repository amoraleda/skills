---
name: learning
description: Create developer-friendly learning documentation for technical topics (Kubernetes, Terraform, internal tools, etc.). Use when the user wants to document technical concepts, create learning materials, explain complex topics to developers, or asks about creating documentation with examples, diagrams, Q&A testing, and FAQs.
---

# Learning Documentation Generator

This skill helps create clear, digestible learning documentation for developers who need to learn technical concepts (Kubernetes, Terraform, internal tools, processes, etc.).

## How to Use This Skill

### Triggering the Skill

This skill works **only within Cursor's chat interface** (not from terminal). It is automatically discovered when you mention relevant keywords:

- "I want to create learning documentation"
- "Help me document this technical concept"
- "Create learning materials for [topic]"
- "Process this content into developer-friendly docs"

### Explicit Invocation

If automatic discovery doesn't work, reference the skill directly:

```
@.cursor/skills/learning/SKILL.md - help me document [topic]
```

Or mention the skill name:

```
Use the learning skill to process this content: [content]
```

### Resuming Work in a New Session

When returning to continue documenting:

- "I want to continue creating learning documentation. Here's the next topic: [content]"
- "Process the content in the source file I provide"

### Important Limitations

- **Chat only**: Skills are a Cursor IDE feature and cannot be triggered from terminal/CLI
- **Interactive**: The Q&A testing step requires conversation, making this inherently chat-based

---

## Output Location

All documentation is saved to: `~/cursor-learning/`

The base directory structure:
```
~/cursor-learning/
├── index.md              # Master index of all learning documents
├── kubernetes/           # Example category folder
│   ├── pods.md
│   └── services.md
├── terraform/            # Another category folder
│   └── modules.md
└── [custom-folder]/      # User-chosen folders
```

### Folder Selection (REQUIRED)

**Before creating any documentation**, you MUST ask the user which folder to use:

```markdown
---

## 📁 Where should I save this documentation?

The learning documentation will be saved to `~/cursor-learning/`.

**Please choose or specify a subfolder:**

1. `kubernetes/` - Kubernetes-related topics
2. `terraform/` - Terraform and IaC topics
3. `tools/` - Internal tools and utilities
4. `processes/` - Team processes and workflows
5. **Custom** - Specify your own folder name

*Reply with a number (1-5) or type a custom folder name*

---
```

Wait for the user to respond before proceeding.

---

## Recommended Cursor Modes

For the best experience, switch between Cursor modes during the workflow:

| Workflow Step | Recommended Mode | Why |
|---------------|------------------|-----|
| **1. Input & Planning** | **Ask Mode** | Discuss the content, clarify scope, ask questions |
| **2. Folder Selection** | **Ask Mode** | Choose where to save the documentation |
| **3. Writing Documentation** | **Agent Mode** | Create and edit files |
| **4. Q&A Testing** | **Ask Mode** | Interactive questioning without file changes |
| **5. Updating FAQ/Docs** | **Agent Mode** | Modify documentation based on Q&A |
| **6. Reviewing & Refining** | **Ask Mode** | Discuss improvements without accidental edits |

> 💡 **Tip**: If you ask a question about the documentation and it reveals something unclear, switch to Agent Mode to update the document.

---

## Workflow Overview

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  1. INPUT       │ ──▶ │  2. FOLDER      │ ──▶ │  3. PROCESS     │ ──▶ │  4. READ        │ ──▶ │  5. TEST        │
│  Raw content    │     │  Choose folder  │     │  Write docs     │     │  User reads doc │     │  Q&A session    │
└─────────────────┘     └─────────────────┘     └─────────────────┘     └─────────────────┘     └─────────────────┘
                                                                                                        │
                                                                                                        ▼
                                                                                               ┌─────────────────┐
                                                                                               │  6. FINALIZE    │
                                                                                               │  Update FAQ     │
                                                                                               └─────────────────┘
```

---

## Step 1: Receive Content

Accept content from the user in one of two ways:
- **File**: User provides a path to source content
- **Chat**: User pastes content directly in conversation

---

## Step 2: Folder Selection

**ALWAYS** prompt the user to choose a folder before writing documentation. See the "Folder Selection (REQUIRED)" section above.

After the user chooses:
1. Create the folder if it doesn't exist: `~/cursor-learning/<chosen-folder>/`
2. Proceed to write documentation

---

## Step 3: Process and Write Documentation

Create documentation following the template in [template.md](template.md).

### Document Header (REQUIRED)

Every document MUST start with this notice box:

```markdown
> **📚 Interactive Documentation**
> 
> This document was created using the **learning** skill. For the best learning experience:
> 1. Read through the document first
> 2. Return to Cursor chat and answer the Q&A questions
> 3. Ask questions if something is unclear — the document will be updated!
> 
> To modify or improve this document, use: `@.cursor/skills/learning/SKILL.md`
```

### Documentation Structure

Each topic document MUST include these sections in order:

1. **Interactive Documentation Notice** (header box above)
2. **Title & TL;DR** - What is this? One sentence summary.
3. **Overview** - 2-3 paragraphs, no jargon.
4. **Why It Matters** - Why should a developer care?
5. **Key Concepts** - Break down the main ideas with simple analogies.
6. **How It Works** - Visual diagram (Mermaid) showing relationships/flow.
7. **Practical Examples** - Real code/config examples with comments.
8. **Common Pitfalls** - What mistakes to avoid.
9. **FAQ** - Questions and answers (populated after Q&A session).
10. **Glossary** - Define technical terms used in the document.
11. **External Resources** - Links to official docs and tutorials.

### Writing Guidelines

- **Target audience**: Developers unfamiliar with the topic
- **Tone**: Friendly, clear, no unnecessary jargon
- **Analogies**: Use real-world comparisons (e.g., "A Pod is like a shipping container")
- **Examples**: Always include working code/config snippets
- **Diagrams**: Use Mermaid syntax for all diagrams
- **Glossary**: Add any technical term that might be unfamiliar

### Diagram Types to Use

```mermaid
%% Architecture diagrams
graph TB
    A[Component] --> B[Component]

%% Sequence diagrams for flows
sequenceDiagram
    User->>Service: Request

%% State diagrams for lifecycles
stateDiagram-v2
    [*] --> Running
```

---

## Step 4: Prompt User to Read

After writing the documentation, **always** prompt the user:

```markdown
---

## 📖 Next Step: Read the Documentation

I've created the documentation at `~/cursor-learning/<folder>/<topic>.md`.

**Please take a few minutes to read through it**, then come back here and let me know you're ready for the Q&A session.

When you're ready, just say: "I've read it, let's do the Q&A"

---
```

Wait for the user to confirm they've read the document before proceeding to Q&A.

---

## Step 5: Test Understanding (Q&A Session)

After the user confirms they've read the documentation:

1. Prepare 5 questions about the content
2. Questions should cover:
   - Basic concept understanding
   - Practical application
   - Common pitfalls
3. Ask questions **ONE AT A TIME**
4. Wait for user response before showing the next question
5. Provide immediate feedback after each answer

### Question Flow

Present questions one by one with a progress indicator. Use this format:

```markdown
---

## 🧠 Q&A Session

---

### Question 1 of 5

> **[Question text]**

a) Option A  
b) Option B  
c) Option C  
d) Option D

---

*Reply with your answer (a, b, c, or d)*
```

After the user answers, provide feedback:

```markdown
---

### ✅ Correct! (or ❌ Incorrect)

[Brief explanation of why the answer is correct/incorrect]

---

### Question 2 of 5

> **[Next question]**

...
```

For open-ended questions:

```markdown
---

### Question 5 of 5 (Open-ended)

> **[Question text]**

*Reply in your own words*
```

### After All Questions

Show a summary:

```markdown
---

## 📊 Results

| # | Question | Your Answer | Result |
|---|----------|-------------|--------|
| 1 | [Short question summary] | [answer] | ✅ |
| 2 | [Short question summary] | [answer] | ❌ |
| ... | ... | ... | ... |

**Score: X/5 (XX%)**

### Key Takeaways
- [Main learning point from incorrect answers]
- [Any clarifications needed]

---
```

---

## Step 6: Finalize and Update Documentation

After the Q&A session, update the documentation:

### When User Asks a Question

If the user asks a question about the documented topic:

1. **If the answer IS in the document but unclear**: 
   - Update the document to explain it better
   - Add the Q&A to the FAQ section

2. **If the answer is NOT in the document**:
   - Add the explanation to the appropriate section
   - Add the Q&A to the FAQ section

3. **If the answer IS clear in the document**:
   - Just add the Q&A to the FAQ section

> 💡 **Important**: Every question from the user is valuable feedback. If they asked, others will too!

### FAQ Format

```markdown
## FAQ

### Q: [Question from Q&A or user]
**A**: [Clear, concise answer]

### Q: [Another question]
**A**: [Answer with example if helpful]
```

### Glossary Format

```markdown
## Glossary

| Term | Definition |
|------|------------|
| **CRD** | Custom Resource Definition - extends Kubernetes with new resource types |
| **Controller** | A program that watches resources and takes action to match desired state |
| **Reconciliation** | The process of comparing desired state vs actual state and making corrections |
```

---

## Update the Index (REQUIRED)

After creating a new document, **always update** `~/cursor-learning/index.md`:

1. Add a link to the new document under the appropriate section
2. Use format: `- [Topic Title](<folder>/filename.md) - Brief description`

Example:
```markdown
## Kubernetes
- [ConsuelaService](kubernetes/consuela-service.md) - Deploy microservices with a simple YAML file
- [Pods](kubernetes/pods.md) - Understanding the smallest deployable unit

## Terraform
- [Modules](terraform/modules.md) - Reusable infrastructure components
```

If the index doesn't exist, create it with the structure shown in the "Index Template" section below.

### Index Template

```markdown
# Learning Documentation Index

> This index is automatically maintained by the **learning** skill.
> 
> To add new documentation, use: `@.cursor/skills/learning/SKILL.md`

## Categories

<!-- Add new categories as needed -->

### Kubernetes
<!-- Kubernetes-related documentation -->

### Terraform
<!-- Terraform and IaC documentation -->

### Tools
<!-- Internal tools and utilities -->

### Processes
<!-- Team processes and workflows -->

---

*Last updated: [Date]*
```

---

## Session Continuity

This workflow supports multi-session work:

- **To pause**: User can stop at any step
- **To resume**: User says "continue with learning docs" and provides context
- **Progress tracking**: Note which step was last completed

---

## Example Topics

See [examples.md](examples.md) for a complete example of a documented topic.

---

## Quick Reference

| Element | Format |
|---------|--------|
| Code blocks | Use language-specific syntax highlighting |
| Diagrams | Mermaid in ```mermaid blocks |
| Commands | `inline code` for short, code block for multi-line |
| File paths | `path/to/file.yaml` |
| Technical terms | **Bold** for key terms, add to Glossary |
| Warnings | > ⚠️ **Warning**: Important caution |
| Tips | > 💡 **Tip**: Helpful suggestion |
| Document header | Always include the Interactive Documentation notice |
| Output location | `~/cursor-learning/<user-chosen-folder>/` |
