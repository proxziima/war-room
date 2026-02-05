---
stepsCompleted: [1, 2, 3, 4, 5, 6]
status: completed
inputDocuments:
  - '_bmad-output/brainstorming/brainstorming-session-2026-02-05.md'
  - '_bmad-output/planning-artifacts/research/technical-nextjs-reactnative-expo-cross-platform-research-2026-02-05.md'
date: 2026-02-05
author: Vinicius
---

# Product Brief: war-room

## Executive Summary

War Room is a visual multi-agent decision platform where AI agents with incompatible priorities deliberate problems in parallel, make reasoning transparent, and forge conclusions through structured conflict rather than consensus-seeking. It replaces the loneliness of modern decision-making — where solo founders, technical leaders, and operators carry consequential choices without real opposition — with an environment where ideas must earn their right to exist.

Unlike chat-based AI tools that optimize for speed, coherence, and helpfulness, War Room optimizes for **epistemic resistance**: durable, role-bound disagreement that preserves tradeoffs instead of smoothing them away. The product's core value is not faster answers but **decisions users are willing to stand behind weeks or months later** — because they watched those decisions survive genuine opposition.

War Room's defensible moat is **temporal gravity**: the more decisions a user makes inside the platform, the more institutional reasoning accumulates — past conclusions become reusable constraints, agents carry context forward, and the cost of leaving becomes epistemic, not financial. The user isn't losing a tool; they're losing the organizational memory of *why* things were decided.

---

## Core Vision

### Problem Statement

Modern decision-makers — solo founders, technical leaders, and operators — face a structural problem: they carry real accountability for consequential decisions but rarely have access to strong, disagreeing peers when those decisions actually happen. They rubber-duck in Notion, role-play objections in their heads, or prompt AI to argue with them, knowing it won't truly push back.

Current AI tools make this worse by design. They optimize for coherence and helpfulness, which quietly drives users toward affirmation and premature convergence. The result is a double pain: **risk blindness** at the moment of deciding ("Am I missing something obvious?") and **epistemic anxiety** in the days after ("Did I fool myself?"). Even good decisions feel fragile when they haven't survived real opposition.

### Problem Impact

- **Pre-decision:** Decision-makers can't honestly hold two incompatible positions with equal force. They subconsciously weaken counterarguments or let them collapse early. AI structurally converges toward the user's framing, regardless of how adversarial the prompt.
- **Post-decision:** Without visible evidence that a conclusion survived pressure, confidence remains hollow. Leaders can't explain *why* a path was chosen, what was rejected, or what risks were consciously accepted — making decisions hard to defend and easy to second-guess.
- **Compounding cost:** Decisions involving irreversibility and second-order effects — architecture, strategy, pricing, org design — create lock-in. Being wrong doesn't just hurt once; it compounds downstream. The cost of unexamined confidence grows with every dependent decision built on top of it.

### Why Existing Solutions Fall Short

| Current Approach | Core Limitation |
|---|---|
| **ChatGPT / AI persona prompts** | Stateless and structurally sycophantic — converges toward user's framing regardless of instruction |
| **Trusted advisors** | Valuable but scarce, asynchronous, and eventually lose the thread of past decision logic |
| **Slack / team debates** | Unstructured, no memory, no accountability for reasoning quality |
| **Pre-mortem frameworks** | Closest to War Room's rigor, but high-friction, manual, and require the user to perform their own skepticism |
| **Decision journals** | Retrospective documentation, not active opposition — captures *what* was decided, not *how* it was stress-tested |

All existing approaches share a common failure: they are **stateless** (no accumulated reasoning across sessions), **sycophantic** (tend toward agreement), or **manual** (require the user to generate their own resistance). None provide durable, role-bound disagreement that carries institutional memory forward.

### Proposed Solution

War Room is a visual, multi-agent decision environment where:

- **Role-bound AI agents** (PM, Architect, Skeptic, Risk Analyst) deliberate problems through structured debate phases — exploration, challenge, synthesis, convergence — with each agent protecting distinct priorities and constraints.
- **Reasoning is externalized and visible.** The user watches ideas collide, mutate, get challenged, and either survive or die. Conclusions are earned artifacts, not generated outputs.
- **The user participates, not commands.** Human input enters the deliberation as a tagged intervention — a constraint, a preference, a veto — that agents evaluate, challenge, and may resist. Authority comes from argument quality, not role.
- **Conclusions travel as first-class artifacts.** Room outputs are named, traceable decisions with attached rationale, rejected alternatives, and documented objections. They can be imported as constraints into future rooms, creating a living decision graph.
- **Institutional memory accumulates.** Past decisions quietly inform future deliberations. The platform becomes the organizational brain — switching away means losing the accumulated reasoning history of *why* things were decided.

### Key Differentiators

1. **Engineered Friction** — War Room's irreducible kernel. Decisions are not generated; they are forged through collision of role-bound constraints and visible reasoning. Speed is deliberately sacrificed for credibility.
2. **Temporal Gravity** — The more you use War Room, the harder it becomes to leave. Not because of data lock-in, but because accumulated institutional reasoning — past conclusions, accepted constraints, evolving agent context — creates epistemic switching cost.
3. **Post-Decision Confidence** — War Room isn't just a pre-decision tool; it's a receipt you carry after. The visible process of opposition becomes the evidence that quiets epistemic anxiety later.
4. **Boundary Discipline** — War Room refuses to be a productivity tool for trivial decisions. It classifies decision weight and reserves full deliberation for choices where being wrong compounds. "If everything feels like a war, the wars stop mattering."
5. **Constitutional Governance** — Agents have rights (to dissent, to block shortcuts, to surface risk). Users have powers (override, veto, final decision). Influence is earned through argument, but agency is never ceded to the system.

---

## Target Users

### Primary Users

**Alex — Solo Technical Founder (Beachhead User)**
- **Context:** Seed-stage fintech founder, architecting alone, making irreversible technology bets without engineering peers to challenge him.
- **Use Case:** Simulates a full engineering lead meeting — pitting a Backend Architect against a Frontend Lead to stress-test whether a pivot to mobile-first architecture is actually viable.
- **Pain:** Re-teaches his product philosophy and tech stack constraints to a fresh ChatGPT window every morning. Decisions feel shallow because they haven't survived real opposition.
- **Success:** Stops paying the "context tax." Agents carry forward conclusions from prior rooms. Architecture decisions come with documented rationale, rejected alternatives, and acknowledged risks.

**Sarah — Head of Product (Growth-Stage Startup)**
- **Context:** Leading product at a 20-person startup, facing a high-stakes feature cut decision where sunk cost bias and team attachment cloud judgment.
- **Use Case:** Deploys a PM agent to defend user value while Backend and Frontend Developer agents expose the technical debt and true maintenance cost of keeping the feature.
- **Pain:** Can't get honest opposition from her own team (they're too close to the work) and doesn't have time to build a structured pre-mortem from scratch.
- **Success:** Walks into the team meeting with a Decision Artifact that shows the reasoning, the tradeoffs, and why the cut is justified — reducing alignment debt and emotional friction.

**Marcus — VP of Engineering (Scale-Up)**
- **Context:** VP of Engineering at a scaling company, deciding build-vs-buy for a data pipeline — a decision with 2+ year lock-in implications.
- **Use Case:** Uses a Code Architect agent to flag long-term maintenance risks, integration complexity, and hidden costs that a vendor salesperson would never surface.
- **Pain:** Vendor demos are optimized to sell, not to stress-test. Internal teams have build bias. Neither side gives him an honest view of the 18-month cost landscape.
- **Success:** Gets a conclusion artifact with explicit tradeoff mapping — what each path costs, what each path risks, and what assumptions would need to be true for each to succeed.

### Secondary Users

**Team Members (Decision Consumers)**
- Receive generated Decision Artifacts showing exactly *why* a call was made — reducing "alignment debt" and eliminating the "because I said so" dynamic. They don't use War Room directly but benefit from its outputs.

**Board Members / Advisors (Confidence Validators)**
- Review Pros/Cons + Rationale artifacts to verify the founder's process is rigorous, not just intuitive. War Room outputs serve as evidence of disciplined decision-making during fundraising and board reviews.

**Future Hires (Institutional Memory Consumers)**
- Use the office "file cabinet" — the accumulated decision graph — to understand the historical context of the codebase, product strategy, or organizational structure they just inherited. They learn *why* things are the way they are, not just *what* exists.

### User Journey (Beachhead: Solo Technical Founder)

| Stage | Experience | Key Moment |
|---|---|---|
| **Discovery** | Finds War Room via viral content ("Why your AI-assisted decisions feel shallow"). Hook is "Epistemic Resistance" — the promise of genuine stress-testing, not affirmation. | "This isn't another ChatGPT wrapper." |
| **First Session** | Describes a tech stack dilemma. System recommends role-specific agents (Backend Architect, PM). Sees Activity Signals — agents visibly thinking, stalling, conflicting. | "This is simulating real cognitive load, not just generating text." |
| **Session 2 (Aha Moment)** | Opens a new room. Agents immediately propose constraints from the previous room's conclusion. Realizes the system remembers institutional logic. | "I've stopped paying the context tax." |
| **Week 4 (Habit Formation)** | War Room becomes a weekly decision ritual for high-stakes, systemic choices. Trivial decisions stay outside. | "I only open War Room when being wrong would compound." |
| **Month 3 (Infrastructure)** | Triggers the "Hand-off Ritual" — earned conclusions transform into granular Jira Epics with user stories and technical tasks. Each ticket carries a lineage link back to the deliberation, rejected alternatives, and governing constraints. | "I can trace any Jira task back to the argument that created it." |

---

## Success Metrics

### User Success Metrics

| Metric | What It Measures | Signal |
|---|---|---|
| **Context Tax Elimination** | Agents carry forward constraints from prior rooms without user re-explanation | Alex starts a new room and doesn't re-paste his tech stack or competitive landscape |
| **Alignment Debt Reduction** | Decision Artifacts reduce downstream questioning and re-litigation | Sarah's team stops challenging pivots because the reasoning is visible in the file cabinet |
| **Decision Velocity** | Time from problem framing to earned conclusion decreases over repeated use | Users spend less time circling and more time executing on conclusions they trust |
| **Conclusion Travel Rate** | Conclusions leave War Room and enter the execution layer | Rooms end with Jira exports, constraint imports into new rooms, or artifact references by secondary users |
| **Post-Decision Confidence** | Users stand behind decisions weeks/months later without re-opening the same question | Reduced re-litigation of past decisions; conclusions referenced as settled constraints |

### Anti-Metric: The Ghost Room

The critical failure signal is the **Ghost Room** — a completed deliberation whose conclusions never travel. If users finish rooms but never trigger a Jira export, never reference the conclusion in a future room, and never share the Decision Artifact with their team, War Room is being used as a theatrical chatbot rather than a decision system that shapes real-world work. Ghost Room rate must be tracked and actively driven down.

### Business Objectives

| Timeframe | Objective | Core Metric |
|---|---|---|
| **3 Months** | Prove the "Aha" moment | **Session 2 Retention Rate** — the percentage of users who return for a second room after experiencing agents that remember context. This proves that once a user stops paying the context tax, they abandon generic chat tools for high-stakes decisions. |
| **12 Months** | Achieve institutional lock-in | **Team/Enterprise Tier Conversion** — driven by the accumulated Decision Graph. A year's worth of organizational reasoning becomes too valuable to leave behind. The switching cost is epistemic, not financial. |

### Key Performance Indicators

| KPI | Definition | Target |
|---|---|---|
| **Session 2 Retention** | % of users who complete a second room within 14 days of their first | Primary leading indicator of product-market fit |
| **Conclusion Travel Rate** | % of completed rooms where the conclusion is exported (Jira, shared, or imported into a new room) | Core health metric — conclusions must leave the room |
| **Ghost Room Rate** | % of completed rooms with zero downstream references (no export, no import, no share) | Anti-metric — must trend downward |
| **Deja Vu Conversion Rate** | % of free users who convert to Pro within 7 days of re-prompting behavior (manually re-pasting context that a persistent agent would remember) | Primary monetization trigger — measures the exact moment the context tax becomes intolerable |
| **Decision Graph Depth** | Average number of cross-room constraint references per user over time | Measures institutional memory accumulation and lock-in strength |
| **Free-to-Pro Conversion** | % of free users upgrading to Pro tier | Driven by the Deja Vu Moment — not by paywalls or nags, but by felt cognitive friction |
| **Pro-to-Enterprise Conversion** | % of Pro users upgrading to Team/Enterprise tier | Driven by organizational adoption — when the Decision Graph becomes a team asset, not just a personal tool |

### Monetization Conversion Logic

The conversion funnel is engineered by cognitive friction, not artificial restriction:

1. **Free Tier** — Fully functional deliberation with role-based agents. Agents are competent but structurally amnesiac — every room starts from scratch.
2. **The Deja Vu Moment** — The system detects re-prompting behavior (user manually re-pasting context from a prior session). This is the conversion trigger — measured, not manufactured.
3. **Pro Tier Offer** — "Stop paying the context tax." Unlocks persistent, situated agents that carry the user's worldview, competitive landscape, and past decisions forward.
4. **Enterprise Trigger** — When multiple team members reference the same Decision Graph, the product becomes organizational infrastructure — too embedded to remove.

---

## MVP Scope

### Core Features (V1)

**1. Structured Multi-Agent Deliberation**
- Role-based specialist agents (PM, Backend Architect, Frontend Lead, Skeptic) with distinct priorities and reasoning patterns
- Structured debate phases: exploration → challenge → synthesis → convergence
- Agents hold durable, role-bound positions — disagreement is maintained, not smoothed away
- Engineered friction: agents resist premature convergence and challenge weak arguments

**2. The Stage (Visual Deliberation Layer)**
- A spatial "stage" where agents occupy distinct positions — not a full isometric office, but enough to signal "this is an organization, not a conversation"
- Role Presence: agents are visually distinct entities identified by the role they protect
- Activity Signals: agents visibly "think," "stall," "disagree," or "concede" — the trust mechanism of Witnessed Reasoning
- Not text-only chat — spatial presence is the minimum visual layer that separates War Room from a chatbot

**3. Human-in-the-Loop (Async Text)**
- User input enters as tagged interventions: constraint, preference, veto, or open question
- Agents evaluate, challenge, and may resist user input — the user participates, not commands
- Constitutional governance: agents have rights (dissent, block), users have powers (override, veto, final decision)

**4. Named Conclusion Artifacts**
- Rooms produce Named Conclusions — first-class decision artifacts with:
  - Earned recommendation with rationale
  - Pros/cons and explicit tradeoffs
  - Rejected alternatives and why they were eliminated
  - Documented objections and minority positions
  - Acknowledged risks and governing constraints
- Conclusions are stored in the office "file cabinet" — a visible, browsable decision history

**5. Conclusions That Travel (Lightweight Persistent Memory)**
- Named Conclusions can be manually imported into new rooms as pre-loaded constraints
- Agents reference imported conclusions when relevant — the "Session 2 aha"
- This is the minimum viable institutional memory: not full RAG, but enough to prove that decisions accumulate rather than reset
- The mechanic that distinguishes War Room from a well-prompted chatbot

**6. Decision Triage (Boundary Discipline)**
- Problem-driven onboarding: describe your problem, system recommends agent composition and room format
- Lightweight triage that signals when a problem may not warrant a full deliberation — "This might not need a War Room"
- Protects the product's authority by reserving full engagement for decisions where being wrong compounds

### Out of Scope for MVP

| Feature | Rationale for Deferral | Target Tier |
|---|---|---|
| **Full Living Office (isometric map, desks, walking agents)** | The Stage proves the spatial thesis; the full office is a polish layer, not a trust mechanism | V2 |
| **Custom/User-Defined Agents** | V1 proves value with curated role specialists; customization is Pro-tier creative control | Pro |
| **RAG-Grounded Agents** | Agents seeded with user's codebase/docs — powerful but requires significant infrastructure | Pro |
| **Persistent Agent Memory (full)** | V1 uses manual conclusion import; full agent memory that carries across all sessions is Pro | Pro |
| **Real-Time Collaboration** | V1 is a solo experience; multiplayer adds massive complexity without proving the core thesis | V2+ |
| **Executable Outputs (Jira/GitHub export)** | The Hand-off Ritual is a growth feature, not a thesis-proving feature | Pro/Enterprise |
| **Dependency Chains (room-to-room DAG)** | Manual conclusion import proves the mechanic; automated chaining is scale infrastructure | Enterprise |
| **Audio/Voice HITL** | Async text intervention is the minimum meaningful HITL | Enterprise |
| **Agent Personalities (humor, moods, emotes)** | Identity must be strictly bound to what the role protects, not how it emotes — a governing principle | Never |
| **Speed Features (Auto-Resolve, Quick Room, Skip)** | Violates "never optimize outcome over process" — a load-bearing wall | Never |
| **Autonomous Alignment / Guardrail Effect** | Requires deep integrations and a mature Decision Graph to be meaningful | 3-Year Vision |

### MVP Success Criteria

**Primary Success Gate: Context Tax Recovery Rate (Session 2 Retention)**

The single metric that validates the thesis: *How many users start a second room and successfully pull in a conclusion or constraint from their first session?*

- If Alex returns to have a second earned argument that builds on the first → thesis proven
- If users only use War Room for one-off sessions → we're a theatrical wrapper, not an institutional memory system

**Supporting Validation Signals:**

| Signal | What It Validates |
|---|---|
| Users complete deliberation (don't abandon mid-room) | Engineered Friction is engaging, not frustrating |
| Conclusions are referenced after the room closes | Conclusions carry weight beyond the session |
| Users describe decisions as "earned" or "stress-tested" (qualitative) | The trust mechanism of Witnessed Reasoning works |
| Ghost Room Rate stays below threshold | War Room is shaping real-world work, not performing theater |
| Users choose War Room over ChatGPT for high-stakes decisions | Category differentiation is felt, not just claimed |

### Future Vision

**Year 1: Decision Tool for Technical Leaders**
- Prove the thesis with solo founders and technical leaders
- Nail the Session 2 aha moment and Conclusion Travel mechanic
- Validate monetization through the Deja Vu conversion trigger

**Year 2: Organizational Reasoning Platform**
- Expand from solo use to team adoption — the Decision Graph becomes a shared organizational asset
- Full Living Office with the spatial metaphor fully realized
- Executable Outputs: Jira epics, GitHub PRs, and architecture docs flow directly from earned conclusions with lineage
- RAG-grounded agents seeded with company codebases, competitive landscapes, and domain knowledge
- Dependency chains: rooms form a DAG of decisions with traceable causality

**Year 3: Institutional Memory Infrastructure**
- **Source of Truth for Intent** — War Room becomes the only system in the corporate stack that knows *why* things were decided. Jira knows *what happened*. Slack knows *what was said*. War Room knows *why it was chosen*.
- **Institutional Memory as a Service** — New hires onboard by exploring the Decision Graph. Two years of earned context without a single meeting.
- **Autonomous Alignment (Guardrail Effect)** — Named Conclusions become Active Monitors. A "Security-First" architecture decision triggers alerts when a PR bypasses the decided protocols. War Room "wakes up" and flags misalignment before work proceeds.
- **Post-Decision Accountability** — 30-day Validation Checks: "We decided X to achieve Y. Based on execution data, are we seeing the expected result, or should we reopen the War Room?"
- **Living Decision Map** — The Decision Graph transforms from a historical archive into a living causal map. Not just tracking what was decided, but the success rate of organizational judgment over time.

**The 3-Year Thesis:** A company doesn't just *use* War Room — it *thinks inside it*. The switching cost isn't data. It's collective intelligence.
