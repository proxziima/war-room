---
stepsCompleted:
  - step-01-init
  - step-02-discovery
  - step-03-success
  - step-04-journeys
  - step-05-domain
  - step-06-innovation
  - step-07-project-type
  - step-08-scoping
  - step-09-functional
  - step-10-nonfunctional
  - step-11-polish
  - step-12-complete
inputDocuments:
  - '_bmad-output/planning-artifacts/product-brief-war-room-2026-02-05.md'
  - '_bmad-output/planning-artifacts/research/technical-nextjs-reactnative-expo-cross-platform-research-2026-02-05.md'
  - '_bmad-output/brainstorming/brainstorming-session-2026-02-05.md'
documentCounts:
  briefs: 1
  research: 1
  brainstorming: 1
  projectDocs: 0
classification:
  projectType: 'SaaS B2B Platform (cross-platform)'
  domain: 'AI Decision Support (general)'
  complexity: 'medium'
  projectContext: 'greenfield'
workflowType: 'prd'
date: '2026-02-05'
author: 'Vinicius'
---

# Product Requirements Document - war-room

**Author:** Vinicius
**Date:** 2026-02-05

## Executive Summary

**Product:** War Room — a visual multi-agent decision platform where AI agents with incompatible priorities deliberate problems on a spatial "Stage," make reasoning transparent through Activity Signals, and forge Named Conclusions through structured conflict.

**Core Differentiator:** Epistemic resistance. War Room optimizes for credibility under pressure, not speed or coherence. Users witness decisions being forged — the visual layer IS the trust mechanism.

**Target User (V1):** Alex — solo technical founder making irreversible decisions alone. Seed-stage, technically excellent, strategically isolated. Tired of paying the context tax to stateless AI tools.

**Thesis:** Decisions feel earned when users see them survive genuine opposition. The switching cost is epistemic, not financial.

**Timeline:** 6 weeks to launch. Visual Office is non-negotiable.

## Success Criteria

### User Success

**The Emotional Arc of Success:**

War Room's user success is measured not just by behavior, but by the *absence of epistemic anxiety* — the shift from "did I miss something?" to "this decision was earned."

- **The "Bullet Dodge" Relief**: The peak emotional success moment. An agent surfaces a fatal flaw in a plan the user was about to commit months to. The feeling isn't disappointment — it's relief. War Room just saved runway, reputation, or irreversible technical debt.
- **The "Quiet Confidence"**: The user closes the laptop knowing the decision survived genuine opposition. They stop seeking validation from friends or advisors because the room's debate was more rigorous than any external conversation could be. Post-decision anxiety is replaced by the weight of earned process.
- **The "Cognitive Exhale"**: In Session 2+, the user types a new problem and agents already carry forward their tech stack, risk tolerance, and past decisions. The context tax disappears. Thinking begins where it left off, not from scratch.

**Measurable User Success Signals:**

| Signal | What It Measures | Success Threshold |
|---|---|---|
| Context Tax Elimination | Agents carry forward constraints without re-explanation | User doesn't re-paste context in Session 2+ |
| Alignment Debt Reduction | Decision Artifacts reduce downstream questioning | Team stops re-litigating decisions with visible reasoning |
| Decision Velocity | Time from problem framing to earned conclusion decreases with use | Measurable decrease by Session 4+ |
| Post-Decision Confidence | Users stand behind decisions weeks/months later | Reduced re-opening of previously concluded rooms |

### Business Success

**Thesis Validation Thresholds (3-Month Gate):**

| Metric | Target | Failure Signal | What Failure Means |
|---|---|---|---|
| **Session 2 Retention** | **> 40%** within 14 days | < 40% | Context Tax relief isn't felt — War Room is a novelty, not a habit |
| **Conclusion Travel Rate** | **> 25%** of rooms | < 10% | "Rooms don't talk, conclusions travel" is a bug, not a feature — Decision Graph thesis collapses |
| **Ghost Room Rate** | **< 20%** of completed rooms | > 20% | Engineered Friction is too high for the payoff — conclusions don't carry enough weight to act on |
| **Deja Vu Conversion Rate** | Track and establish baseline | No re-prompting behavior detected | Free-to-Pro conversion trigger isn't materializing |

**12-Month Objective:** Institutional lock-in via Team/Enterprise tier conversion — driven by the accumulated Decision Graph becoming too valuable to abandon. Switching cost is epistemic, not financial.

### Technical Success

| Metric | Target | Measurement |
|---|---|---|
| Canvas rendering FPS (mobile) | >= 60fps | React Native Perf Monitor |
| Canvas rendering FPS (web) | >= 60fps | Chrome DevTools |
| API response time (p95) | < 200ms | Vercel Analytics |
| Time to Interactive (web) | < 2s | Lighthouse |
| App startup time (iOS) | < 1.5s | Expo EAS Insights |
| Undo/redo latency | < 16ms (1 frame) | Custom profiling |
| Code sharing ratio | >= 60% | Lines in packages/ vs apps/ |
| Test coverage (canvas-core) | >= 90% | Vitest coverage |

### Measurable Outcomes

**Primary Success Gate:** Session 2 Retention > 40% — the single metric that validates the thesis. If Alex returns to have a second earned argument that builds on the first, the product works. If users only use War Room for one-off sessions, it's a theatrical wrapper.

**Anti-Metric:** Ghost Room Rate. A completed deliberation whose conclusions never travel is the critical failure signal. War Room must shape real-world work, not perform theater.

**Conversion Logic:** Conversion is driven by cognitive friction, not artificial restriction. The Deja Vu Moment — when a user recognizes they're re-explaining context the system should already know — is the natural upgrade trigger. "Stop paying the context tax."

## Product Scope

### MVP — Minimum Viable Product

**The Irreducible Kernel: "The Stage + The Artifact"**

5 core features that prove the thesis of earned conclusions through witnessed reasoning:

**1. Structured Multi-Agent Deliberation**
- Role-based specialist agents (PM, Backend Architect, Frontend Lead, Skeptic) with distinct priorities
- Structured debate phases: exploration, challenge, synthesis, convergence
- Durable, role-bound disagreement — agents resist premature convergence
- Constitutional governance: agents have rights (dissent, block), users have powers (override, veto)

**2. The Stage (Visual Deliberation Layer)**
- Spatial "stage" where agents occupy distinct visual positions
- Activity Signals: agents visibly "think," "stall," "disagree," or "concede"
- Trust mechanism of Witnessed Reasoning — the visual layer IS the product differentiator
- Not a full isometric office — minimum viable spatial presence that separates War Room from a chatbot

**3. Human-in-the-Loop (Async Text)**
- User input enters as tagged interventions: constraint, preference, veto, open question
- Agents evaluate, challenge, and may resist user input
- The user participates, not commands — authority comes from argument quality

**4. Named Conclusion Artifacts**
- Rooms produce first-class decision artifacts with: earned recommendation, pros/cons, rejected alternatives, documented objections, acknowledged risks
- Conclusions stored in the "file cabinet" — a visible, browsable decision history

**5. Manual Conclusion Import (Lightweight Institutional Memory)**
- Users can manually select past conclusions from a list to import as pre-loaded constraints into new rooms
- Agents reference imported conclusions when relevant — the "Session 2 aha"
- No automated smart suggestions or ML in V1 — manual selection proves the utility

**Deferred from MVP:**
- Decision Triage UI / "Rejection Wizard" — trust early adopters to self-select meaningful problems
- Automated constraint suggestion engine — manual import proves the mechanic first

### Growth Features (Post-MVP)

| Feature | Trigger for Build | Tier |
|---|---|---|
| Decision Triage UI | If impatient-user churn signal appears | Free |
| Custom/User-Defined Agents | Pro upsell after users hit generic agent ceiling | Pro |
| RAG-Grounded Agents (user's codebase/docs) | Pro upsell for situated deliberation | Pro |
| Persistent Agent Memory (full) | Beyond manual import — agents carry full context | Pro |
| Executable Outputs (Jira/GitHub export) | Conclusion Travel Rate plateau — need execution bridge | Pro/Enterprise |
| Automated Constraint Suggestions | Manual import usage proves demand | Pro |

### Vision (Future)

**Year 1:** Decision tool for technical leaders — nail Session 2 retention, Conclusion Travel, and Deja Vu conversion.

**Year 2:** Organizational reasoning platform — team adoption, full Living Office, executable outputs, RAG-grounded agents, dependency chains (room-to-room DAG).

**Year 3:** Institutional memory infrastructure — Source of Truth for Intent. War Room becomes the only system that knows *why* things were decided. Named Conclusions become Active Monitors. The Decision Graph transforms from archive to living causal map.

**The 3-Year Thesis:** A company doesn't just *use* War Room — it *thinks inside it*. The switching cost isn't data. It's collective intelligence.

## User Journeys

### Journey 1: Alex — The Solo Founder's First War (Happy Path)

**Who:** Alex, 29, seed-stage fintech founder. Former senior engineer at Stripe. Left to build a payment orchestration platform. Technically excellent, strategically alone. Makes every architecture decision in his apartment at 1 AM with a cold coffee and a ChatGPT window that agrees with whatever he types last.

**The Pain:** Alex has been re-pasting his tech stack, competitive landscape, and product philosophy into ChatGPT every morning for four months. He prompts it to "argue against" his decisions, but the arguments fold the moment he pushes back. He knows the opposition is theatrical. His decisions feel fast but fragile — he can't explain *why* he chose a particular path, only that it felt right at the time.

**Opening Scene — Discovery:**
Alex sees a tweet: *"Why your AI-assisted decisions feel shallow."* The hook is "epistemic resistance" — not faster answers, but answers that survive contact with real opposition. He clicks through. The landing page doesn't promise productivity. It promises *decisions he'll still believe in next quarter.* "This isn't another ChatGPT wrapper." He signs up.

**Rising Action — First Session:**
Alex describes his dilemma: he's about to commit to a microservices architecture for his payment orchestration layer. It'll take 3 months to build and is nearly irreversible at his stage. He types the problem into a new room. The system recommends a Backend Architect and a PM agent — two roles with structurally incompatible priorities.

The room begins. It's not instant. The Backend Architect visually "loads" the problem, stalls on a complexity concern, then opens with: *"Microservices at your team size is a scaling solution for a scaling problem you don't have yet."* The PM agent pushes back: *"But the payment domain has natural service boundaries — orchestration, ledger, webhooks. A monolith will fight you at integration points."*

Alex watches. The agents aren't performing debate — they're holding positions that won't collapse. The Backend Architect doesn't concede under PM pressure; instead, it escalates: *"If you build microservices now, you're paying the coordination tax on every feature for the next 12 months. At one engineer, that's not a tax — it's a full-time job."*

Alex intervenes: *"What about a modular monolith with clear domain boundaries?"* His input enters the room as a tagged constraint. The PM agent evaluates it and agrees it preserves service boundaries without the coordination overhead. The Backend Architect pauses visibly — then concedes: *"That eliminates my primary objection. But I want to flag: the ORM layer needs to enforce module boundaries from day one, or this quietly becomes a ball of mud."*

**Climax — The Bullet Dodge:**
The room converges. The Named Conclusion reads: *"Modular monolith with enforced domain boundaries. Microservices deferred until team exceeds 3 engineers or transaction volume exceeds 10K/day."* Attached: the Backend Architect's acknowledged risk (ORM boundary enforcement), the PM's rejected alternative (full microservices), and the Skeptic's minority position (*"Re-evaluate in 6 months — the modular monolith pattern has a history of degrading without strict discipline"*).

Alex reads the artifact. He didn't just get an answer — he watched it survive. The Backend Architect nearly killed his original plan, and he feels *relief*, not disappointment. He was about to spend a quarter of his runway on architecture his team can't support. The room saved him from a mistake he couldn't see because he was too close.

**Resolution — Session 2 (The Aha Moment):**
Three days later, Alex opens a new room: *"Should I use Stripe Connect or build a custom payment routing layer?"* Before he types his tech stack, the PM agent opens with: *"Given the modular monolith decision from Room 1, a custom routing layer would need to live within the existing module boundaries. Does that constraint hold?"*

Alex stares at the screen. He didn't paste anything. The agent *remembered*. The prior conclusion traveled into this room as a pre-loaded constraint. He doesn't have to re-teach his world. The context tax is gone.

He thinks: *"I've stopped paying the context tax."*

**New Reality:**
By Week 4, War Room is a weekly ritual for irreversible decisions. Alex doesn't use it for everything — only for choices where being wrong compounds. Trivial decisions stay in his head. War Room is the place he goes when the cost of self-deception is measured in months, not minutes. He closes the laptop after each session with quiet confidence, not the anxious hum of "did I miss something?"

### Journey 2: Alex — Reopening a Past Decision (Edge Case)

**Who:** Same Alex, 3 months later. His modular monolith is working, but transaction volume is growing faster than expected. A potential enterprise client needs multi-currency support, and the monolith's payment module is straining at the seams.

**Opening Scene — The Doubt:**
Alex opens the file cabinet and stares at Room 1's conclusion: *"Modular monolith. Microservices deferred until team exceeds 3 engineers or transaction volume exceeds 10K/day."* He's at 8K/day and climbing. The Skeptic's minority position rings in his head: *"Re-evaluate in 6 months."* It's been 3 months. He opens a new room.

**Rising Action — The Reopen:**
Alex imports the original conclusion as a constraint and frames the new problem: *"Transaction volume approaching the 10K threshold. Enterprise client needs multi-currency. Is it time to extract the payment module into a service?"*

The Backend Architect loads the original constraint and immediately flags: *"The threshold was 10K/day. You're at 8K with acceleration. But the original rationale was team size, not just volume — you're still at 2 engineers. Extracting a service doubles your operational surface with half the staff needed to maintain it."*

The PM agent pushes: *"The enterprise client represents 40% of projected ARR. Losing them because the monolith can't handle multi-currency is an existential risk, not a technical preference."*

**Climax — The Evolved Decision:**
The room doesn't simply reverse the old decision. It *evolves* it. The new conclusion: *"Extract payment routing as a standalone service. Keep ledger and webhooks in the monolith. Hire a second backend engineer before extraction begins — do not extract at current team size."* The original conclusion is marked as *superseded*, with a clear lineage link showing what changed and why.

Alex sees the decision graph growing. Room 1 → Room 7. The Skeptic's 3-month warning was prescient. The system didn't just remember the decision — it remembered the conditions under which it should be revisited.

**Resolution:**
Alex doesn't feel like he made a mistake in Room 1. He feels like the decision was *right then* and *evolved now*. The lineage is visible. If a future hire asks "why is payment routing a separate service but ledger isn't?", the answer is traceable — not tribal.

### Journey 3: Sarah — The Feature Cut

**Who:** Sarah, 34, Head of Product at a 20-person SaaS startup. Her team spent 4 months building a "Smart Recommendations" feature. Usage data shows it's underperforming — 6% adoption, high maintenance cost, and it's blocking the roadmap. Sarah suspects it should be cut, but the team is emotionally attached. The engineer who built it is her most senior developer. She can't get honest opposition from people too close to the work.

**Opening Scene — The Political Minefield:**
Sarah can't run a fair internal debate. The feature's creator will defend it. The junior PMs will defer to her opinion. The CTO will optimize for whatever ships fastest. She needs agents that hold positions without social cost — a PM agent defending user value, a Backend agent exposing true maintenance cost, and a Skeptic that challenges sunk cost reasoning.

**Rising Action — The Uncomfortable Truth:**
Sarah frames the room: *"Should we cut Smart Recommendations? 6% adoption, 15% of engineering maintenance budget, blocking 2 roadmap items."*

The PM agent opens hard: *"6% adoption after 4 months isn't underperforming — it's a signal that the feature solves a problem users don't have. The 94% who ignore it aren't wrong."*

The Backend agent piles on: *"Maintenance cost isn't 15% — it's 15% of engineering time plus the opportunity cost of 2 blocked roadmap items. Real cost is closer to 30% of team velocity."*

Sarah intervenes with a constraint: *"What if we simplify it instead of cutting it? Reduce scope to basic recommendations."*

The Skeptic resists: *"Simplifying a feature with 6% adoption doesn't change the denominator. You'd spend 2 weeks building a simpler version of something 94% of users don't want. The sunk cost is already sunk. The question isn't 'can we save it?' — it's 'what would we build instead with that 30% velocity?'"*

**Climax — The Earned Cut:**
The conclusion artifact reads: *"Cut Smart Recommendations. Reallocate engineering capacity to [Roadmap Item A] and [Roadmap Item B]. Communicate cut to team with attached rationale, rejected alternatives (simplify, defer, A/B test), and acknowledged risks (6% of users lose a feature they use)."*

Sarah didn't make this call alone. She didn't make it politically. She made it through visible opposition that she can show her team.

**Resolution — Alignment Debt Eliminated:**
Sarah walks into the team meeting with the Decision Artifact. She doesn't say "because I said so." She shows the reasoning: the PM agent's user data analysis, the Backend agent's true cost calculation, the Skeptic's challenge to her own "simplify" compromise. The engineer who built the feature reads the rejected alternatives — his instinct to simplify was considered and specifically addressed.

The team doesn't love the decision. But they stop fighting it. The reasoning is visible. Alignment debt: zero.

### Journey 4: The Decision Consumer — Receiving an Artifact

**Who:** David, 27, mid-level frontend engineer on Sarah's team. He built the recommendation engine's UI. He's been told the feature is getting cut in tomorrow's team meeting. He's frustrated — he spent 6 weeks on this. He opens the Decision Artifact that Sarah shared in Slack.

**Opening Scene — Defensive Mode:**
David clicks the link expecting a management memo — a polished justification written after the decision was already made. He's ready to be angry.

**Rising Action — The Reasoning Trail:**
Instead, he sees the full deliberation structure. The PM agent argued *for* user value — David's own position — and lost on the data. The Backend agent calculated maintenance cost at 30% of team velocity, including opportunity cost David hadn't considered. Most importantly, he sees that Sarah herself proposed a "simplify" alternative — and the Skeptic challenged it with reasoning David finds hard to argue with.

He reads the rejected alternatives section. His instinct — "just simplify it" — is listed, considered, and specifically addressed. He wasn't ignored. His position was represented and tested.

**Climax — The Shift:**
David reads the Skeptic's minority position: *"If recommendation adoption increases to 15%+ organically over the next quarter, revisit this cut."* The decision isn't permanent — it's conditional. There's a path back if the data changes.

He doesn't feel great. But he stops feeling dismissed. The process was more rigorous than any meeting he's been in. His work was weighed, not waved away.

**Resolution — Viral Potential:**
In the next sprint planning, David references the Decision Artifact when a teammate proposes a similar low-adoption feature: *"Can we run this through the same process Sarah used? I want to see if the PM agent defends it or kills it."*

David isn't a War Room user. But he just became a War Room advocate. The artifact traveled from Sarah's room into David's vocabulary. He doesn't use the product — but the product's output changed how he thinks about decisions.

### Journey Requirements Summary

| Journey | Capabilities Revealed |
|---|---|
| **Alex — Happy Path** | Room creation, agent recommendation, structured debate phases, activity signals (visual thinking/stalling), tagged user interventions, Named Conclusion artifacts, file cabinet storage, manual conclusion import across rooms |
| **Alex — Edge Case** | Conclusion reopening/evolution, decision lineage tracking, superseded conclusion marking, constraint re-evaluation against new data |
| **Sarah — Feature Cut** | Multi-agent deliberation with domain-specific framing, pros/cons with true cost analysis, rejected alternatives documentation, shareable Decision Artifacts |
| **David — Decision Consumer** | Artifact readability for non-users, reasoning trail visibility, rejected alternatives section, conditional/minority positions, shareability via external links (Slack, email) |

**Cross-Journey Capability Requirements:**
- Room lifecycle: create → deliberate → conclude → store → import → reopen
- Activity Signals on the Stage (visual cognitive load)
- Tagged user interventions (constraint, preference, veto, question)
- Named Conclusion Artifacts with full structure (recommendation, pros/cons, rejected alternatives, objections, risks, minority positions)
- File cabinet with browsable decision history
- Manual conclusion import as constraints
- Decision lineage (Room N → Room N+3 supersedes)
- Shareable artifacts for non-users (Decision Consumers)

## Innovation & Novel Patterns

### Detected Innovation Areas

**1. Epistemic Resistance as a Product Category**
War Room proposes a new product category where the core value is *resistance to premature agreement* — not speed, not coherence, not helpfulness. No existing AI product optimizes for credibility under pressure. This is a category inversion, not a feature improvement.

**2. Multi-Agent Structured Deliberation**
Existing "debate mode" features in AI tools are persona prompts on a single model — episodic, stateless, and structurally sycophantic. War Room proposes role-bound agents with incompatible priorities that maintain disagreement structurally. The architecture IS the product — replicating this value requires rebuilding around institutional memory as a first principle, not prompting better.

**3. Conclusions as First-Class Artifacts**
No AI tool treats outputs as named, portable, versionable decision objects with provenance and lineage. War Room's Named Conclusions are institutional artifacts that travel between rooms, get imported as constraints, form a decision graph, and carry attached rationale, rejected alternatives, and minority positions.

**4. Temporal Gravity / Epistemic Lock-In**
A novel retention mechanic where switching cost is epistemic, not financial or data-based. The more decisions a user makes inside War Room, the more accumulated reasoning they lose by leaving. Past conclusions become reusable constraints, agents carry context forward, and the decision graph becomes organizational infrastructure.

**5. Engineered Friction as Feature**
Every AI product optimizes for speed-to-answer. War Room deliberately sacrifices speed for trust. Visible cognitive load, drag, stalling, and the noise-to-structure transition are design choices that create believable deliberation. "Speed is the enemy of trust." Latency becomes a feature, not a bug.

### Market Context & Competitive Landscape

| Competitor Category | What They Do | Why War Room Is Different |
|---|---|---|
| **ChatGPT / Claude / AI chat** | Single-voice, stateless, coherence-optimized | War Room: multi-voice, persistent, credibility-optimized |
| **"Debate mode" features** | Persona prompts on one model — episodic, collapsible | War Room: role-bound agents with durable disagreement and institutional memory |
| **Decision frameworks (pre-mortems, DACI)** | Manual, high-friction, require user to generate own resistance | War Room: automated structured opposition with visual witnessing |
| **Notion / Confluence** | Document *what* was decided | War Room: captures *why* and *how* it was decided, with full reasoning trail |
| **Advisory boards / consultants** | Valuable but scarce, async, eventually lose the thread | War Room: always available, carries full context, never forgets |

**The Moat:** Competitors can copy the *performance* of deliberation (multi-persona, visible disagreement) but not the *commitment model* (decisions as durable state, temporal gravity, epistemic switching cost). Adding a "debate mode" to a chat product is a response primitive. War Room's value lives in what happens *after* the room — and that requires architectural commitment competitors can't bolt on.

### Validation Approach

**Primary Validation: Session 2 Retention > 40%**
The thesis is proven if users return for a second room and successfully pull in a conclusion from their first session. This validates both "epistemic resistance works" (they trusted the first room enough to come back) and "conclusions travel" (institutional memory has value).

**Supporting Validation Signals:**
- Users complete deliberation without abandoning mid-room (friction is engaging, not frustrating)
- Conclusions are referenced after the room closes (artifacts carry weight beyond the session)
- Users describe decisions as "earned" or "stress-tested" in qualitative feedback
- Ghost Room Rate stays below 20% (conclusions shape real-world work)
- Users choose War Room over ChatGPT for high-stakes decisions (category differentiation is felt)

**Fastest Path to Thesis Validation:**
Build the irreducible kernel (Stage + Artifact + Manual Import) and get it in front of 10-20 solo technical founders. If Session 2 behavior emerges organically — users importing prior conclusions without being prompted to — the thesis is alive.

### Risk Mitigation

| Innovation Risk | Severity | Mitigation |
|---|---|---|
| "Epistemic resistance" feels like slowness, not value | High | Activity Signals make cognitive load visible — the user sees *why* it takes time. Drag must feel like thinking, not buffering. |
| Multi-agent deliberation produces incoherent noise | Medium | Structured debate phases (exploration → challenge → synthesis → convergence) provide arc. Noise-to-structure transition is the designed experience. |
| Users don't import conclusions (manual friction too high) | Medium | V1 file cabinet with simple list selection. If import rate is low, investigate whether the mechanic or the UX is the bottleneck before adding automation. |
| Competitors ship "debate mode" that captures 80% of value | Low | The 80% they capture is the performance. The 20% they can't is the commitment model — institutional memory, temporal gravity, decision lineage. That 20% is where all the retention lives. |
| Engineered friction drives users away before they experience value | High | First session must deliver a "Bullet Dodge" moment within 5-10 minutes. If the friction payoff takes too long, users churn before the thesis can prove itself. |

## SaaS B2B Platform Requirements

### Architecture Philosophy

**"Rocket ship, not cruise liner."** — V1 is a single-player experience for the solo technical founder. Every enterprise feature that doesn't serve Alex on Day 1 is deferred until paying customers demand it.

### Multi-Tenancy Model

| Tier | Model | Implementation |
|------|-------|----------------|
| **V1 (Free/Pro)** | Single-player | `user_id` only. No org structure, no invites, no shared workspaces. |
| **V2 (Team)** | Multi-tenant shared | Row Level Security (RLS) in PostgreSQL. Logical isolation by `org_id`. Shared infrastructure. |
| **Enterprise** | Dedicated (on demand) | Single-tenant isolation only for six-figure contracts. Not a V1 concern. |

**V1 Scope**: Zero multi-tenancy code. If you're logged in, you own everything.

### Permission Model

| Tier | Model | Roles |
|------|-------|-------|
| **V1** | Binary | Authenticated = God mode. Create, delete, burn it down. |
| **Team (Future)** | Role-based | Admin (billing/settings), Editor (run rooms), Observer (read-only Decision Graph) |

**V1 Scope**: No RBAC. No permission checks beyond authentication. One user, one workspace, full control.

### Integration Strategy

| Tier | Approach | Details |
|------|----------|---------|
| **V1** | Magic Clipboard | Formatted copy button for Linear/Notion/Jira. Headers, checkboxes, structured markdown. Zero OAuth, zero API complexity. Feels like integration, costs nothing. |
| **Pro** | Real Integrations | Jira API, GitHub API — conclusions push directly to external systems with lineage links. |
| **Enterprise** | SSO + Custom | SAML/OIDC, API access for custom workflows, webhook subscriptions. |

**V1 Scope**: Copy-to-clipboard with smart formatting. That's the integration layer.

### Compliance & Security

| Requirement | V1 | Future |
|-------------|-----|--------|
| **Encryption** | ✓ At rest + in transit (standard) | — |
| **GDPR** | ✓ "Delete My Account" button | Data export, consent management |
| **SOC 2** | ✗ Series A problem | Type II when enterprise sales require it |
| **Audit Logs** | ✗ Deferred | Enterprise tier feature |
| **Data Residency** | ✗ Deferred | EU hosting option for Enterprise |

**V1 Scope**: Encryption defaults + account deletion. If a prospect asks for SOC 2 today, they're not our customer yet.

### Platform Requirements (Cross-Platform)

| Platform | V1 Target | Technology |
|----------|-----------|------------|
| **Web** | Primary | Next.js 15+ App Router, Vercel deployment |
| **iOS** | Primary | Expo SDK 54+, React Native, App Store |
| **Android** | Deferred | Expo supports it — trivial to add post-launch |

**V1 Scope**: Web + iOS. Same codebase (monorepo), platform-specific renderers for the Stage.

## Project Scoping & Phased Development

### MVP Strategy & Philosophy

**MVP Approach:** Problem-Solving MVP with Visual-First Constraint

The thesis is that decisions feel earned when users *witness* them being forged. The visual office isn't a UI layer on top of deliberation — it IS the product. "Overseeing an organization" is the core feeling that separates War Room from every chat-based AI tool.

**Non-Negotiable Anchor:** The Stage (Visual Office) ships in V1, no exceptions.

**Timeline:** 6 weeks to launch.

**Priority Hierarchy:** Visual Polish > Feature Completeness. If scope conflicts arise, cut features (Custom RAG, advanced integrations) before compromising the visual experience.

### MVP Feature Set (Phase 1)

**Core User Journey Supported:** Alex — Solo Founder's First War (Happy Path + Session 2 Aha Moment)

**Must-Have Capabilities (The Irreducible Kernel):**

| Feature | Why Non-Negotiable |
|---------|-------------------|
| **The Stage (Visual Office)** | Trust mechanism. Users must *see* agents deliberate. No Stage = no product. |
| **Structured Multi-Agent Deliberation** | Role-bound disagreement is the core value. Agents hold incompatible positions. |
| **Activity Signals** | Agents visibly think, stall, disagree, concede. The visual layer IS the credibility signal. |
| **Async Text HITL** | User participates as constraint-setter, not commander. Minimum viable interaction. |
| **Named Conclusion Artifacts** | Rooms produce first-class decision objects. Conclusions travel to file cabinet. |
| **Manual Conclusion Import** | Session 2 depends on pulling prior conclusions into new rooms. Proves institutional memory. |
| **Magic Clipboard Export** | Formatted copy for Linear/Notion. Zero OAuth complexity. |

**Technical Fallback Strategy:**

If high-fidelity Skia/PixiJS rendering proves too complex for 6-week timeline:
- **Hard-Coded Visual Approach**: Simpler static pixel-art rooms with clever state changes
- Agents physically move to "deliberation table" when room starts
- State-driven animations (idle → thinking → speaking → conceding) over procedural animation
- The office must *feel* alive through smart state transitions, even if not fully animated

**Explicitly Deferred from MVP:**
- Decision Triage UI / "Rejection Wizard"
- Custom/User-Defined Agents
- RAG-Grounded Agents
- Full Persistent Agent Memory (beyond manual import)
- Real API integrations (Jira/GitHub)
- Multi-tenancy / Team features
- Android

### Post-MVP Features

**Phase 2 — Growth (Post-Launch, Demand-Driven):**

| Feature | Trigger to Build |
|---------|-----------------|
| Decision Triage UI | Impatient-user churn signal appears |
| Custom Agents | Users hit generic agent ceiling, request Pro upsell |
| Real Integrations (Jira/GitHub) | Conclusion Travel Rate plateaus — need execution bridge |
| Persistent Agent Memory | Manual import proves value, users want automation |

**Phase 3 — Expansion (Year 2+):**

| Feature | Trigger to Build |
|---------|-----------------|
| Team/Multi-tenancy | Enterprise demand materializes with contracts |
| Full Living Office | V1 Stage proves the spatial thesis, polish follows |
| RAG-Grounded Agents | Pro users need situated deliberation |
| Dependency Chains (Room DAG) | Decision Graph complexity requires it |
| SSO/Enterprise Security | Six-figure contracts require it |

### Risk Mitigation Strategy

**Technical Risks:**

| Risk | Severity | Mitigation |
|------|----------|------------|
| Stage rendering too complex for 6 weeks | High | Hard-Coded Visual fallback — static pixel-art with state-driven animations. Ship visual, polish later. |
| Cross-platform parity (Web vs iOS) | Medium | Monorepo with shared canvas-core logic. Platform-specific renderers (PixiJS web, Skia mobile). Accept minor visual differences. |
| Multi-agent orchestration complexity | Medium | Start with 2-3 agents max per room. Structured debate phases constrain chaos. |

**Market Risks:**

| Risk | Severity | Mitigation |
|------|----------|------------|
| "Epistemic resistance" feels like slowness | High | Activity Signals make cognitive load visible. Drag must feel like thinking, not buffering. First session delivers "Bullet Dodge" in 5-10 minutes. |
| Users don't return for Session 2 | High | Primary success gate. If Session 2 Retention < 40%, thesis fails — investigate whether context tax relief isn't felt or conclusions don't carry weight. |
| Competitors ship "debate mode" | Low | They copy performance, not commitment model. Moat is what happens *after* the room. |

**Resource Risks:**

| Risk | Severity | Mitigation |
|------|----------|------------|
| 6-week timeline too aggressive | Medium | Visual Office is the floor. Cut features before cutting visual quality. Magic Clipboard over real integrations. Manual import over automation. |
| Solo founder capacity limits | Medium | Monorepo maximizes code sharing. Lean on Expo/Vercel managed infrastructure. No custom DevOps. |

## Functional Requirements

### Room Management

- **FR1:** User can create a new deliberation room with a problem statement
- **FR2:** User can view a list of all their rooms (active and completed)
- **FR3:** User can open and re-enter any existing room
- **FR4:** User can close/conclude a room when deliberation is complete
- **FR5:** User can delete a room and its associated data
- **FR6:** System recommends agent composition based on problem framing

### Agent Deliberation

- **FR7:** Agents hold distinct role-based positions (PM, Backend Architect, Frontend Lead, Skeptic)
- **FR8:** Agents deliberate through structured phases (exploration → challenge → synthesis → convergence)
- **FR9:** Agents maintain durable disagreement and resist premature convergence
- **FR10:** Agents can challenge, question, and push back on other agents' positions
- **FR11:** Agents can concede positions when presented with stronger arguments
- **FR12:** Agents reference imported constraints when relevant to deliberation
- **FR13:** System limits room to 2-4 agents per deliberation

### Visual Experience (The Stage)

*Note: FR14-FR19 are the trust mechanism. The Stage is how users witness reasoning being forged. These are non-negotiable.*

- **FR14:** User views deliberation on a spatial "stage" where agents occupy distinct visual positions
- **FR15:** Agents display as pixel-art characters with role-identifiable visual design
- **FR16:** Agents show Activity Signals indicating current state (idle, thinking, speaking, stalled, disagreeing, conceding)
- **FR17:** Agents physically transition between states (e.g., move to deliberation table when room starts)
- **FR18:** Visual layer reflects cognitive load and deliberation progress
- **FR19:** Stage renders consistently across web and iOS platforms

### Human Participation (HITL)

- **FR20:** User can submit text input during active deliberation
- **FR21:** User input is tagged by type (constraint, preference, veto, open question)
- **FR22:** Agents evaluate and respond to user input within deliberation
- **FR23:** Agents can resist or push back on user input with reasoning
- **FR24:** User can override agent objections with explicit acknowledgment
- **FR25:** User retains final decision authority on room conclusions

### Conclusions & Artifacts

- **FR26:** Room produces a Named Conclusion artifact upon completion
- **FR27:** Conclusion includes: earned recommendation with rationale
- **FR28:** Conclusion includes: pros and cons with explicit tradeoffs
- **FR29:** Conclusion includes: rejected alternatives and why eliminated
- **FR30:** Conclusion includes: documented objections and minority positions
- **FR31:** Conclusion includes: acknowledged risks and governing constraints
- **FR32:** User can edit conclusion name and summary before finalizing
- **FR33:** Conclusions are marked with creation date and source room

### Institutional Memory

- **FR34:** User can browse all past conclusions in a "file cabinet" view
- **FR35:** User can search/filter conclusions by name, date, or content
- **FR36:** User can select past conclusions to import into a new room as constraints
- **FR37:** Imported conclusions are visible to agents and referenced in deliberation
- **FR38:** System tracks decision lineage (which conclusions supersede others)
- **FR39:** Superseded conclusions show link to newer conclusions

### Export & Sharing

- **FR40:** User can copy conclusion to clipboard with structured formatting (Magic Clipboard)
- **FR41:** Clipboard export formats for Linear, Notion, and generic markdown
- **FR42:** User can generate a shareable read-only link to a conclusion artifact
- **FR43:** Non-users (Decision Consumers) can view shared artifacts without login
- **FR44:** Shared artifacts display full reasoning trail, rejected alternatives, and minority positions

### User Account & Workspace

- **FR45:** User can sign up and authenticate via Clerk (email, OAuth)
- **FR46:** User can sign out and sign back into their workspace
- **FR47:** User can delete their account and all associated data (GDPR)
- **FR48:** User workspace persists across web and iOS platforms
- **FR49:** User can access their workspace from any device after authentication

## Non-Functional Requirements

### Performance

**Visual Rendering:**
- Stage rendering maintains ≥60fps on target devices (web: Chrome/Safari, iOS: iPhone 11+)
- Activity Signal state transitions complete within 100ms (no perceptible lag)
- Agent movement animations feel intentional, not janky

**API & Backend:**
- API response time (p95) < 200ms for all user-initiated actions
- Time to Interactive (web) < 2s on 4G connection
- App startup time (iOS) < 1.5s

**Character-State Signals (Replaces Generic Loading):**
- **API Latency:** Agents display "thinking" pose for normal delays; "tired" pose for extended waits (>3s)
- **Context Load:** Agents show "sweat" or "overload" frames when processing heavy context windows
- **Stalled Threads:** Agents display "blocked" state if reasoning hits a wall or needs user input
- No spinners, no progress bars — the characters ARE the diagnostic layer
- Technical limitations become visible cognitive weight, not UI chrome

**Intentional Latency (Trust Mechanism):**
- Deliberation pacing is *designed*, not performance-limited
- Agent "thinking" pauses are engineered (500ms-2s) to signal cognitive load
- Fast performance is invisible; slow *feels* intentional

### Security

**Data Protection:**
- All data encrypted at rest (database) and in transit (HTTPS/TLS)
- User authentication via Clerk with secure session management
- Room and conclusion data isolated per user (no cross-user data access)

**Compliance:**
- GDPR: User can delete account and all associated data within 30 days
- No sensitive data (payment, health) stored in V1 — compliance floor is low

**Authentication:**
- Clerk handles auth — email/password + OAuth (Google, GitHub)
- Session tokens expire appropriately (Clerk defaults)
- No password storage in application database

### Reliability

**Data Persistence:**
- Room state persists across sessions — users can close browser and return
- Conclusion artifacts are durable — no data loss on room completion
- Cross-device sync: user's workspace accessible from web or iOS after auth

**Graceful Degradation (Character-State Signals):**
- If LLM API is slow: agents show "tired" or "sweating" — no error modals
- If context window is heavy: agents visibly strain under cognitive load
- If reasoning stalls: agents show "blocked" state, not generic error
- Users see *why* the system is working hard, not just *that* it's working

**Availability:**
- Target 99.5% uptime (Vercel/Neon SLA baseline)
- No silent data loss — errors surface to user with recovery options

**Backup & Recovery:**
- Database backups per Neon defaults (point-in-time recovery)
- No user-facing backup/restore in V1 — infrastructure handles it

### Accessibility

**Core Constraint:** War Room is a visual product. The Stage (pixel-art agents, spatial deliberation) is the trust mechanism. Full accessibility would require an alternative non-visual mode, which is out of scope for V1.

**V1 Accessibility Floor:**
- Text chat transcript available alongside visual Stage
- Conclusion artifacts are fully text-readable (no visual-only information)
- Shareable links work with screen readers (artifact content is semantic HTML)
- Color contrast meets WCAG AA for UI controls (buttons, forms)
- Keyboard navigation for core actions (create room, submit input, copy clipboard)

**Future Consideration:**
- Audio/screen-reader mode for deliberation could expand market, but not V1
