# CLASSBRAINSTORMING.md

Collaborative idea board for a future class/workshop on agentic engineering.
Tone goal: practical, credible, low-hype, hands-on.

## Big Framing Ideas

1. "From Prompting to Product Thinking"
- Position the class as software design literacy, not AI novelty.
- Core message: agents are useful when tied to clear constraints and verification loops.

2. "AI As Junior Collaborator"
- Emphasize this is not "AI replaces staff."
- Better framing: "AI accelerates prototyping and documentation while humans own decisions."

3. "Evidence Over Hype"
- Show before/after artifacts: bug report, architectural decision, commit trail, improved outcome.
- Make participants inspect the process, not just outputs.

## Positioning For AI-Averse Stakeholders

1. Risk-managed language
- "Assisted development workflow"
- "Human-in-the-loop quality controls"
- "Reproducible iteration logs"

2. Governance-first framing
- Every change is inspectable in files and commits.
- Every major decision has rationale in durable docs.
- Sensitive tasks can be excluded by policy.

3. Learning outcome framing
- Teaches debugging, systems thinking, documentation, and critical review.
- AI is the medium, engineering judgment is the skill.

## Demo Concepts (No Full Lesson Plan, Just Seeds)

1. Live Failure -> Fix Story
- Start with a known broken behavior (timer ends too early).
- Let the agent propose options.
- Compare patch vs architecture rewrite.
- Debrief: why root-cause framing matters.

2. Constraint Injection Demo
- Add a new non-negotiable constraint mid-run.
- Example: deterministic end-time cannot drift.
- Observe how requirements reshape implementation.

3. Documentation-As-Code Demo
- Show AGENTS.md changing behavior over time.
- Show TEACHABLEMOMENTS.md capturing process decisions.
- Show how memory is externalized into files.

## Workshop Activity Ideas

1. "Prompt to Spec" Drill
- Participants transform vague prompt into explicit acceptance criteria.
- Score clarity, testability, and risk awareness.

2. "Agent Review Board"
- Team A: asks agent for implementation.
- Team B: does code review only from diffs and docs.
- Team C: validates behavior using test checklist.

3. "Autonomy Dial"
- Run same task with low, medium, high autonomy prompting.
- Compare speed, error rate, and trust level.

4. "Failure Taxonomy"
- Participants classify failures: requirements, logic, UX, tooling, auth, environment.
- Then design mitigations for each class.

## Teachable Contrasts (High Value)

1. Parameter Tweaking vs Architecture Fix
- Tweaking randomness did not solve timer correctness.
- Separating timer truth from gameplay style did.

2. Clever Code vs Explainable Code
- Optimized logic is less useful if students cannot reason about it.
- Prioritize inspectable systems and traceable decisions.

3. Demo Success vs Operational Success
- Local prototype can work while deployment/auth flow still blocks.
- Real engineering includes identity, tooling, permissions, and handoff.

## Class Discussion Prompts

1. What should always remain human-owned in agentic workflows?
2. When should an agent stop and ask before continuing?
3. Which artifacts make AI-assisted work trustworthy to others?
4. What does "good enough autonomy" look like in public institutions?

## Assessment Ideas (Lightweight)

1. Decision quality rubric
- Did participants identify constraints?
- Did they validate outcomes?
- Did they document rationale?

2. Diff literacy rubric
- Can participants explain what changed and why?
- Can they identify risk from a patch quickly?

3. Reflection prompts
- "What did the agent do well?"
- "What required human correction?"
- "What would you automate next?"

## Artifact Kit Ideas

1. Template files
- `AGENTS.md` starter template
- `TEACHABLEMOMENTS.md` retrospective template
- "verification checklist" template

2. Scenario cards
- "Timer drift bug"
- "Auth flow blocked"
- "Conflicting stakeholder requirements"

3. Prompt patterns
- "Implement, then verify, then summarize risks."
- "Do not stop at analysis; commit to tested patch."
- "If blocked, produce minimal human handoff commands."

## Library-Specific Angle (Toronto Public Library Context)

1. Public value framing
- Focus on digital literacy and critical AI use.
- Teach citizens how to evaluate AI-assisted outputs.

2. Accessibility and inclusion
- Include non-programmer pathways: process maps, review checklists, plain-language specs.
- Treat coding as one mode, not the only mode.

3. Workforce relevance
- Emphasize transferable skills: problem decomposition, validation, documentation, collaboration.

## Pilot-Friendly Rollout Ideas

1. Start internal
- Small staff sandbox cohort before public programming.

2. Keep scope bounded
- One contained project artifact (like this timer app) with visible progression.

3. Capture outcomes
- Track confidence gains, review quality, and ability to critique agent output.

## Future "Go Wild" Concepts

1. Multi-agent roleplay session
- Architect agent, implementer agent, tester agent, reviewer agent.
- Humans arbitrate disagreements.

2. Narrative debugging theater
- Turn bug reports into "mystery episodes."
- Participants investigate evidence across files/commits.

3. Public-facing exhibit
- A live kiosk showing agent-human iteration timeline for one feature.
- Visitors can inspect prompts, diffs, and final behavior.

## Open Questions For Victor + Codex

1. What audience comes first: staff training, teen programs, adult learners, or mixed?
2. How explicit should AI policy discussion be in session 1?
3. Should coding be optional with parallel no-code analysis tracks?
4. Which success metric matters most for pilot approval?

## Working Rule For This File

- Capture rough ideas quickly first.
- Promote only validated ideas into formal curriculum docs later.

## New Seed From Current Bug (2026-02-17)

1. "Planner vs Physics" mini-lab
- Give learners a bot that picks strong final placements but ignores movement feasibility from spawn.
- Let them observe the mismatch: smart plan, weak execution, premature stall.
- Task: patch with one feasibility heuristic (visibility gate, reachability penalty, or spawn fallback).
- Debrief question: "What is the minimum extra model needed to make planning trustworthy?"

2. "Semantic Integrity" mini-lab
- Show a version where overflow clips silently past the top.
- Ask learners whether this is a rendering issue or a rules issue.
- Patch: enforce top-out at lock-above-top and on garbage displacement overflow.
- Debrief question: "Which failures are visual, and which failures are domain truth?"

3. "Ambiguous State" mini-lab
- Give a build where the agent can neither place nor terminate cleanly.
- Ask learners to define terminal conditions in plain language first.
- Then implement exact code-level gates that enforce those conditions.
- Debrief question: "When users say 'it forgot to play', what state machine rule is missing?"

## New Seed From Progress Mapping Regression (2026-02-19)

1. "Same Percent, Different Reality" mini-lab
- Provide one build where UI percent is linear but fill target is eased (`progress^k`).
- Ask learners to predict expected rows at 10%, 25%, 50%.
- Run it and compare observed vs expected behavior.
- Patch options:
- align mapping to linear
- or keep easing but expose both metrics in UI
- Debrief question: "When is a mismatch a bug vs an intentional product decision?"

## New Seed From Simulation Speed Request (2026-02-27)

1. "Control Surface Mapping" mini-lab
- Give learners a build with one speed variable (`MOVE_INTERVAL_MS`) and ask them to make runs complete 10x faster.
- Most will first tune movement cadence and discover it is the wrong lever.
- Then introduce separate controls:
- movement cadence
- elapsed-time multiplier
- Debrief question: "Which system behavior are you actually controlling with each knob?"

2. "Testability as Feature" discussion
- Prompt: "Is a 10x speed mode only for developers, or also for users?"
- Compare two framings:
- debug utility
- rehearsal/story preview mode
- Debrief question: "When does internal tooling become product value?"

