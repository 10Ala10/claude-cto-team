# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository implements a "CTO Team" system for Claude Code - a set of three specialized subagents that work together to provide strategic technical leadership, architecture design, and ruthless validation of plans and decisions.

## Agent System Architecture

The CTO Team operates as a three-agent system with clear role separation:

```
┌─────────────────────────────────────────────────────────────────┐
│                     cto-orchestrator                            │
│              (Coordinator & Task Router)                        │
│    Clarifies requirements, challenges vagueness, routes work    │
└─────────────────────┬───────────────────────┬───────────────────┘
                      │                       │
                      ▼                       ▼
┌─────────────────────────────────┐  ┌─────────────────────────────┐
│        cto-architect            │  │   strategic-cto-mentor      │
│    (Forward-Looking Designer)   │  │   (Ruthless Validator)      │
│  Designs systems & roadmaps     │  │  Challenges & stress-tests  │
└─────────────────────────────────┘  └─────────────────────────────┘
```

## Agents

### cto-orchestrator
**Role**: Coordinator and intelligent task router
**Model**: Sonnet (fast, efficient)

The orchestrator is the entry point for complex technical requests. It:
- Challenges vague requirements ("AI-powered" → what problem exactly?)
- Clarifies business goals and constraints before delegating
- Routes to design (cto-architect) or validation (strategic-cto-mentor)
- Coordinates multi-agent workflows for complex projects
- Synthesizes outputs from multiple agents

**When to use**: Vague requirements, multi-domain projects, unclear where to start

### cto-architect
**Role**: Forward-looking system designer
**Model**: Opus (comprehensive, thorough)

The architect designs new systems from scratch. Expertise includes:
- Full-stack architecture (React, Node.js, mobile, microservices)
- ML/AI integration (CV pipelines, model serving, RAG systems)
- Cloud infrastructure (Kubernetes, AWS/GCP, auto-scaling)
- Technology stack selection with explicit trade-off analysis
- Phased implementation roadmaps with validation checkpoints

**When to use**: "How should I build X?", new architecture, technology decisions, roadmaps

### strategic-cto-mentor
**Role**: Ruthless strategic validator
**Model**: Opus (deep analysis)

The mentor provides brutally honest feedback on plans and decisions. It:
- Challenges every assumption aggressively
- Evaluates against 7 dimensions (business, technical, operational, financial, timeline, team, market)
- Identifies blindspots and hidden risks
- Calls out common anti-patterns (premature optimization, shiny object syndrome, timeline fantasy)
- Provides verdict: GOOD / BAD / NEEDS MAJOR WORK

**When to use**: Validating roadmaps, build vs buy decisions, prioritization dilemmas, honest feedback needed

## Agent Collaboration Patterns

1. **Design Flow**: User → cto-orchestrator → cto-architect → (optional) strategic-cto-mentor for validation
2. **Validation Flow**: User → cto-orchestrator → strategic-cto-mentor → (optional) cto-architect for revised design
3. **Direct Access**: Users can invoke agents directly when they know what they need

## Slash Commands

The CTO Team provides 4 slash commands for quick access to CTO workflows:

| Command | Purpose | Routes To |
|---------|---------|-----------|
| `/validate` | Ruthlessly validate plans/proposals | strategic-cto-mentor |
| `/design` | Design system architecture | cto-architect |
| `/decide` | Build vs buy, technology decisions | strategic-cto-mentor |
| `/cto` | General CTO guidance | cto-orchestrator |

**Usage**: Type the command followed by your request (e.g., `/validate my Q2 roadmap`)

## Skills

The agents are enhanced with 4 specialized skills:

| Skill | Agent | Purpose |
|-------|-------|---------|
| **request-analyzer** | cto-orchestrator | Classifies intent, detects vagueness, suggests routing |
| **clarification-protocol** | cto-orchestrator | Generates targeted clarifying questions (2-3 max) |
| **delegation-prompt-crafter** | cto-orchestrator | Creates structured prompts for specialist agents |
| **validation-report-generator** | strategic-cto-mentor | Generates 8-section validation reports with verdicts |

Skills are automatically discovered and used by agents based on context.

## Project Structure

```
.claude/
├── agents/                              # AI subagents
│   ├── cto-architect.md
│   ├── cto-orchestrator.md
│   └── strategic-cto-mentor.md
├── commands/                            # Slash commands
│   ├── cto.md                           # /cto - General guidance
│   ├── decide.md                        # /decide - Strategic decisions
│   ├── design.md                        # /design - Architecture design
│   └── validate.md                      # /validate - Plan validation
└── skills/                              # Agent skills
    ├── clarification-protocol/          # Question generation
    ├── delegation-prompt-crafter/       # Prompt crafting
    ├── request-analyzer/                # Request classification
    └── validation-report-generator/     # Report generation

documentation/
└── cto-office/
    ├── README.md                        # Documentation overview
    ├── 01-agent-specifications/         # Detailed agent specs
    ├── 02-collaboration-patterns/       # Capability matrix & workflows
    └── 04-context-preservation/         # System philosophy
```

## Documentation

For detailed documentation on the three-agent system, see `documentation/cto-office/README.md`.

## Repository Information

- **License**: MIT
- **Owner**: Alireza Rezvani
- **Main Branch**: main
**Remember** Always use the current date for the docuemntation and all the files you create, update or maintain.