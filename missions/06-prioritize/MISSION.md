# Mission 06 — Prioritize

> Mentor: teach a framework (RICE or MoSCoW), but the real lesson is that prioritization forces trade-offs. Make the learner explicitly cut something. A backlog where everything is "must have" is a fail.

## Goal
Turn the feedback themes and ideas into a prioritized list of what Signal should build first, using a real framework.

## Why it matters
Everything feels important. Prioritization is the discipline of saying "this, not that, and here is why" so a team does not spread itself across ten half-built features. The ability to defend a ranked list in a room full of opinions is a core PM and founder superpower.

## What to do
1. Pull the candidate features from your earlier work. The themes from `data-insights.md` and the dealbreakers from `interview-report.md` are your raw backlog (onboarding, integrations, exec summary, trust/traceability, pricing model, mobile, performance).
2. Pick a framework and apply it. Two options:
   - **MoSCoW** (simplest, good default): sort every feature into Must have / Should have / Could have / Won't have. A strong prompt:
     > "Take the feature candidates from my data-insights.md and interview-report.md and sort them with MoSCoW (Must / Should / Could / Won't have) for the MVP. Explain each placement in one line, then name the top 3 Musts. Save to workspace/prioritization.md."
   - **RICE** (more rigorous, uses numbers): score each feature on Reach, Impact, Confidence, Effort, then rank by (Reach x Impact x Confidence) / Effort. If you go this route, ask your mentor to "show me a 2-row example first so I understand the scoring," then do the full table.
     > Worked example to anchor the numbers: "Zendesk integration" might score Reach 8, Impact 3, Confidence 0.9, Effort 3 -> (8x3x0.9)/3 = 7.2. "Mobile fixes" might score Reach 3, Impact 1, Confidence 0.8, Effort 4 -> (3x1x0.8)/4 = 0.6. Higher score = do first.

   If unsure which to use, start with MoSCoW.
3. Force the cut: "what are we explicitly NOT building for the MVP, and why is that okay?"
4. Sanity-check against the decision: "does the top of this list match the wedge in my decision memo? If not, which is wrong?"

## Definition of Done
- `workspace/prioritization.md` exists.
- It applies a named framework (RICE or MoSCoW), shows the reasoning/scoring, ranks the items, names the top ~3 for the MVP, and explicitly lists what is being cut.

## Hints (mentor: one at a time)
1. The candidates already exist in their earlier files. They do not need to invent a backlog, just rank the themes they found.
2. RICE forces them to estimate effort, which is where the honest trade-offs appear. Do not let every item be "low effort, high impact."
3. The "Won't / Not now" list is the most important part. A prioritization with no cuts is a wish list.

## What you just learned
A framework turns a pile of good ideas into a defensible sequence, and the real value is in what you choose NOT to do. Prioritization is subtraction.
