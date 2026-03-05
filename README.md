# Cursor Agent Skills

A collection of reusable agent skills intially created for Cursor IDE that enhance AI-assisted development workflows.

## What are Agent Skills?

Agent Skills are structured instructions that teach Cursor's AI agent how to perform specific, repeatable tasks. They provide domain knowledge, workflows, and best practices that the agent can follow to deliver consistent, high-quality results.

## Available Skills

### [Learning Documentation Generator](learning/SKILL.md)

**Path**: `learning/SKILL.md`

Create developer-friendly learning documentation for technical topics (Kubernetes, Terraform, internal tools, etc.).

**Features**:
- Structured documentation with TL;DR, diagrams, and examples
- Interactive Q&A testing to verify understanding
- Automatic FAQ generation from user questions
- Progress tracking across sessions

**Usage**: Ask Cursor to "create learning documentation for [topic]" or reference `@learning/SKILL.md`

### [Speech Coach](speech-coach/SKILL.md)

**Path**: `speech-coach/SKILL.md`

Analyze transcripts of meetings, presentations, or talks to provide actionable communication coaching.

**Features**:
- Detailed analysis of speaking patterns (filler words, structure, clarity)
- Progress tracking across multiple sessions
- Personalized improvement strategies
- Native language considerations for non-native speakers

**Usage**: Ask Cursor to "analyze my speech from this transcript" or reference `@speech-coach/SKILL.md`

## Installation

1. Clone this repository into your Cursor skills directory:

```bash
git clone https://github.com/your-username/skills.git ~/.cursor/skills
```

2. The skills will be automatically discovered by Cursor when you mention relevant keywords in chat.


## License

Apache License 2.0 - See [LICENSE](LICENSE) for details.
