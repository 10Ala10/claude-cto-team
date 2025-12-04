# claude-cto-team

Your personal CTO Team for Claude Code. These subagents challenge your thinking while you plan and execute, providing strategic technical leadership, architecture design, and ruthless honest feedback.

## The Three-Agent System

| Agent | Role | When to Use |
|-------|------|-------------|
| **cto-orchestrator** | Coordinator & Router | Vague requirements, multi-domain projects, unclear where to start |
| **cto-architect** | System Designer | New architecture, "How should I build X?", technology decisions, roadmaps |
| **strategic-cto-mentor** | Ruthless Validator | Validating plans, build vs buy, prioritization, need honest feedback |

## Agent Details

### cto-orchestrator (Sonnet)
The entry point for complex technical requests. Challenges vague buzzwords, clarifies requirements, and routes work to the right specialist.

**Example triggers:**
- "I want to add AI capabilities to my app"
- "Here's my Q2 roadmap, what do you think?"
- "Our app is slow and users are complaining"

### cto-architect (Opus)
Designs comprehensive architectures and implementation roadmaps. 15+ years experience in scalable web/mobile with ML/AI integration.

**Core expertise:**
- Full-stack: React, NextJS, Node.js, React Native, Swift, Kotlin
- Backend: Microservices, PostgreSQL, GraphQL, REST APIs
- ML/AI: Real-time CV pipelines, model serving, vector databases, RAG
- Infrastructure: Kubernetes, Docker, AWS/GCP, multi-region deployments

**Deliverables:**
- Executive summary with timeline and budget estimates
- System architecture with component diagrams
- Technology stack with explicit trade-off analysis
- Phased implementation roadmap with validation checkpoints
- Risk assessment and mitigation strategies

### strategic-cto-mentor (Opus)
Ruthless CTO mentor who stress-tests ideas until they're bulletproof. 20+ years experience, 3 failed startups and 2 successful exits.

**Evaluation dimensions:**
1. Business Impact
2. Technical Risk
3. Operational Risk
4. Financial Risk
5. Timeline Risk
6. Team Risk
7. Market Risk

**Anti-patterns called out:**
- Premature Optimization Trap
- Shiny Object Syndrome
- Technical Debt Denial
- Consensus Paralysis
- Hero Culture
- Build Trap
- Timeline Fantasy

## How They Work Together

```
User Request
     │
     ▼
┌─────────────────────────────────────────┐
│          cto-orchestrator               │
│  Clarifies → Challenges → Routes        │
└────────────────┬────────────────────────┘
                 │
    ┌────────────┴────────────┐
    ▼                         ▼
┌───────────────┐    ┌────────────────────┐
│ cto-architect │    │ strategic-cto-mentor│
│   (Design)    │───▶│    (Validate)      │
└───────────────┘    └────────────────────┘
```

**Design → Validate**: Architect creates design, mentor stress-tests it
**Validate → Design**: Mentor identifies flaws, architect revises

## Installation

1. Copy the agent files to your project:
```
.claude/
└── agents/
    ├── cto-architect.md
    ├── cto-orchestrator.md
    └── strategic-cto-mentor.md
```

2. The agents will be automatically available in Claude Code

## Example Usage

**Architecture Design:**
> "I want to build a mobile app that uses computer vision to identify plants. We expect 100K users in the first year."

→ Routes to **cto-architect** for comprehensive architecture design

**Plan Validation:**
> "Here's my draft Q2 roadmap: migrate to Kubernetes, implement real-time features, refactor payments, launch mobile app."

→ Routes to **strategic-cto-mentor** for ruthless stress-testing

**Build vs Buy:**
> "Should we use OpenAI's API or host our own LLM? We're processing 50K conversations per month."

→ Routes to **strategic-cto-mentor** for TCO analysis and trade-off evaluation

## License

MIT License - Alireza Rezvani
