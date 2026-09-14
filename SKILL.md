---
name: ai-product-builder-framework
description: Guides a user through building a product idea from raw problem to working prototype using a structured 9-step framework (Problem Identification, Problem Validation, Competitive Research, Spec in Markdown, Build Prototype, Internal Testing, User Feedback, Iterate, Develop). Use this skill any time someone wants to build a prototype, validate a product idea, build an app or feature concept, or says things like "I have an idea for...", "help me build a prototype", "I want to build an app/tool/feature", or "how do I know if this is worth building" — even if they don't name the framework explicitly. Also use when someone asks to skip straight to building/coding a product idea without having validated the problem or researched competitors first; this skill should proactively suggest going through validation and research before building. Trigger immediately at the first sign someone is starting a new product or app idea from scratch.
---

# AI Product Builder Framework

A 9-step methodology for going from raw product idea to working prototype — built for PMs and builders who want to move fast without skipping the validation work that makes the build worth doing.

---

## How to use this skill

When someone describes a product idea or asks to build something, **do not jump straight to building**. Instead, ask where they are in the 9 steps and guide them through each phase actively — asking clarifying questions, running the prompts below at each stage, and synthesizing findings before moving forward.

If they've already completed earlier steps, acknowledge that and pick up from where they are. If they insist on skipping directly to building, flag the risk once — then respect their call.

---

## The 9 Steps

### Phase 1: Problem → Prototype

---

#### 1. Problem Identification

Identify a specific, observable, measurable problem to solve.

Before moving on, the user should be able to articulate:
- What changed in user behavior or context that created this problem
- What tradeoff or friction users currently experience
- What they'd expect to see in the data if this is the right problem to solve

**Clarifying questions to ask (one at a time):**
- Who specifically has this problem? How do you know?
- What do they do today instead of using your solution?
- What would "fixed" look like — what behavior would change?

---

#### 2. Problem Validation

Determine if this is actually a problem worth solving — and pressure-test it with someone (or something) actively trying to disprove it.

Run the prompt below. The "3 reasons not to build" section is what separates validation from confirmation-seeking.

**Prompt Template — Problem Validation:**
```
I'm validating a product problem before building anything. Here's the problem statement:

[DESCRIBE THE PROBLEM: what's broken, who it affects, what behavior or data suggests it's real]

Research and report back on:
1. Existing products or features that already try to solve this problem — who's done it, and how
2. Evidence that this pain point is real and meaningful — data, research, user feedback, anything that confirms or challenges the premise
3. The addressable opportunity — how big is this if solved, in terms of [METRIC(S) YOU CARE ABOUT, e.g. engagement, retention, revenue]
4. Three honest reasons this might NOT be worth solving — steelman the case against building this

Be specific and cite sources where possible. Don't just confirm my assumption — tell me if the data doesn't support it.
```

---

#### 3. Competitive Research

Map who else is solving this problem, how, and where the gaps are.

**Prompt Template — Competitive Research:**
```
I'm researching the competitive landscape for [PRODUCT AREA / PROBLEM SPACE].

Competitors to research: [LIST KNOWN COMPETITORS, or identify them yourself]

For each competitor, find:
1. Target customer segment and primary device/platform focus
2. Their core approach to solving [THE PROBLEM]
3. Specific investments or features relevant to [THE PROBLEM] — what have they shipped, and when
4. Pricing model and approximate scale (users/subscribers), if public
5. Their key differentiator
6. Known weaknesses — from user reviews, press coverage, or churn/satisfaction data

After the comparison, synthesize: where is the actual gap? Has anyone solved this fully, partially, or not at all? How big is the lead I'd be chasing, or the head start I'd have?
```

---

#### 4. Spec in Markdown

Write a machine-readable product spec that becomes the build prompt.

One file should do three jobs:
- **Product brief** — states the problem, the success metric, and the scope
- **Architecture doc** — concrete enough to build against (layout, behavior, data flow)
- **Build prompt** — feeds directly into your AI coding tool with no translation step

Feed in the context from steps 1–3 and ask clarifying questions one at a time until there's enough to write the full spec. What's written is what gets built.

**Prompt Template — Spec in Markdown:**
```
I want to build a prototype and need your help turning it into a build-ready spec.

Here's the context:
- Problem: [PASTE FROM STEP 1]
- Validation findings: [PASTE KEY FINDINGS FROM STEP 2]
- Competitive gap: [PASTE GAP SYNTHESIS FROM STEP 3]

Ask me clarifying questions one at a time — about users, scope, success metrics, layout, interactions, data — until you have everything you need. Then write a complete markdown spec I can hand directly to an AI coding tool.
```

---

#### 5. Build Prototype

Hand the spec to an AI coding tool and build.

- Use the markdown spec from Step 4 as the primary input — don't paraphrase it, paste it
- If using Claude Code: the spec becomes the CLAUDE.md file
- Build the simplest version that demonstrates the core behavior — not the full product
- Constrain the build: what is explicitly out of scope for this prototype?

---

### Phase 2: Test → Learn → Ship

---

#### 6. Internal Testing

Test the prototype yourself before showing anyone else.

- Does it do what the spec says?
- Where does it break or feel wrong?
- What would a skeptical stakeholder call out immediately?

Log issues. Fix the critical ones. Don't polish — just make it honest.

---

#### 7. User Feedback

Put the prototype in front of real users (or close proxies).

- Show, don't tell — let them interact without narrating
- Listen for confusion, not just complaints
- The most valuable signal is usually what they *don't* say or do

Capture raw quotes and observations. Resist the urge to explain or defend.

---

#### 8. Iterate

Return to the spec and update it based on what you learned.

- What changed about your understanding of the problem?
- What needs to be rebuilt vs. adjusted?
- Is there a step earlier in the framework you need to re-run?

Repeat steps 5–7 as many times as needed. Iteration is the loop, not the exception.

---

#### 9. Develop

Hand off to engineering — or harden the prototype into a production build.

- The spec (now battle-tested) becomes the engineering brief
- Include: what was validated, what was cut, what the prototype revealed
- If using Claude Code to ship: move from prototype environment to production environment, add error handling, edge cases, and real data

---

## Skill behavior rules

- **Never skip to building** without at least checking whether steps 1–3 have been addressed
- **Guide one step at a time** — don't dump all 9 steps at once
- **Ask clarifying questions one at a time**, not in batches
- **Synthesize findings** before moving to the next step — don't just hand back a template and move on
- **Respect urgency** — if the user insists on skipping validation, flag it once, then help them build
