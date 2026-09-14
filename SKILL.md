# AI Product Builder Framework

A 9-step methodology for taking a product idea from raw problem to working prototype using AI tools throughout.

## The 9 steps

1. **Problem Identification** — Name the specific problem, for whom, and why it matters now.
2. **Problem Validation** — Confirm the problem is real before writing a line of code: talk to people who have it, look for existing evidence, or test the assumption cheaply.
3. **Competitive Research** — Survey what already exists. Identify the gap your approach fills that others don't.
4. **Spec in Markdown** — Write a lightweight spec: what it does, what it doesn't do, and the core user flow. Markdown, not a slide deck — something an AI coding tool can build from directly.
5. **Build Prototype** — Use an AI coding assistant to build a working first version fast. Optimize for "does this prove the idea," not production polish.
6. **Internal Testing** — Use it yourself. Break it. Find the gaps between the spec and the reality.
7. **User Feedback** — Put it in front of a few real users outside your own head. Watch where they get confused before asking what they think.
8. **Iterate** — Fix what testing and feedback surfaced. Repeat steps 6–8 as needed.
9. **Develop** — Once the core loop is validated, invest in the version worth maintaining: better error handling, real infrastructure, and the polish that testing alone won't tell you to add.

## Why this order

Most of the risk in a new product idea is in steps 1–3, not step 5. This framework front-loads validation so the build phase is spent on an idea that's already been pressure-tested, not on the first idea that came to mind.

## Use with Claude

This works well as a Claude skill — point Claude at a raw problem statement and have it walk through each step with you, producing the validation notes, competitive research, and spec as it goes, before writing any code.
