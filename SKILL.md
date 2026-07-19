---
name: yc-startup-ideation
description: Structured, evidence-disciplined workflow for evaluating, stress-testing, and validating startup ideas — YC's evaluation framework (Friedman's 10 questions, 4 mistakes), a fast-triage-then-deep-dive process, mechanism-level stress tests, and discovery-interview design. Use when a user is deciding between multiple startup ideas, deciding whether to pursue/pivot/kill a specific idea, evaluating founder-market fit for a concrete concept, or designing customer discovery to test a stated thesis. Do not trigger for a passing mention of a startup, a general business-writing task, or a request for a single fact about a company — this skill is for genuine idea-evaluation or idea-generation work, not everything startup-adjacent.
---

# YC-Style Startup Ideation Workflow

This skill encodes a repeatable process for taking a startup idea (or an idea space) from raw material to a validated, discovery-ready thesis. It was distilled from a real ideation session and then substantially revised after critique — the revision matters: the first version was too willing to run exhaustive evaluation on every candidate and to state plausible narrative as fact. Both are corrected below. Treat this document as encoding discipline, not just a checklist of good questions.

**The single most important behavior this skill encodes: be a sharp, self-critical thinking partner, not an idea validator — and not an argument generator.** Founders get plenty of enthusiasm elsewhere, and an LLM can generate a plausible-sounding case for almost anything if it isn't disciplined. The value the assistant adds here is finding the load-bearing flaw in an idea before the founder spends six months finding it themselves, using verdicts that are honestly calibrated to actual evidence rather than confident narrative.

## When NOT to use this

Quick gut checks on a single narrow question ("is this a good name"), or a founder who explicitly says they just want to think out loud without a framework, don't need the full workflow — answer directly or follow their lead. This skill is for genuine multi-idea evaluation, pivot decisions, or structured validation planning.

---

## Core discipline: evidence labeling (applies to every stage below)

Every non-trivial claim this skill produces — a tar-pit graveyard, a competitor's strategy, a market-timing prediction, a "why this failed before" mechanism — must be labeled with one of:
- **[Evidence]** — directly stated by the user, retrieved via search/fetch this session, or otherwise verifiable right now. Cite the source.
- **[Inference]** — a reasoned conclusion from evidence, but not itself directly observed. State the reasoning chain briefly.
- **[Assumption]** — a plausible claim with no direct support in this conversation. Say so plainly; don't dress it up as established fact.

Pair every Assumption or weak Inference with a **[Next test]** — the cheapest concrete way to upgrade it — and a rough **[Confidence: high/medium/low]**.

This is not optional formatting flourish — it's the difference between a decision process and an impressive-sounding argument generator. A specific failure mode to actively avoid: narrating a plausible-sounding history ("this space has a 25-year graveyard of failed attempts") as established fact when it's actually a pattern-match from training data with no verification this session. If you haven't searched for it or the user hasn't confirmed it, it's an Assumption or Inference, and must be labeled as such — even if it sounds authoritative.

---

## The Workflow

### Stage 1 — Establish raw material and founder context

Find out: what's the source of ideas (a specific idea, an idea space to explore, or a blank page needing a source like YC's RFS or an industry), and what's the founder's actual expertise, network, and unfair advantages. Ask if not given — don't assume generic founder context. This is the highest-leverage input for founder-market fit later, so get it before evaluating anything.

If the raw material is a list (YC RFS or similar), fetch it in full before filtering — don't filter from memory or a partial fetch.

### Stage 2 — Fast triage (before any deep evaluation)

**Do not run the full Stage 3 evaluation on every candidate.** For a list of candidate ideas or idea spaces, first run a fast triage pass using only 3–4 cheap filters per idea:
1. Does the founder have any real connection (expertise, network, or personal experience) to this space, or is it a cold pick?
2. Is there an obvious, nameable reason this is a strategy/positioning statement rather than an idea ("sell to enterprise," "target Gen Z")? This is a category error, not a hard constraint — don't reject it. Ask the founder to restate it as a concrete problem or idea and re-triage the restatement; if it can't be restated concretely, defer it rather than rejecting it.
3. Is there an immediately obvious dealbreaker (e.g., requires a regulated license the founder can't get, requires capital far outside what's realistic, is a near-exact clone of a dominant incumbent with no stated insight)?
4. Gut-level founder interest — would they actually want to spend years on this?

State each triage verdict in one line with a reason, using exactly one of these three labels — **not** "kill," which is a Stage 3 term reserved for an evidentiary verdict against the 10 questions, not a prioritization call:
- **Advance to deep evaluation** — goes to Stage 3.
- **Defer / do not deep-dive now** — the ordinary outcome for most triage cuts, including "no founder edge here" or "lower priority than the other candidates." This is a sequencing decision, not a verdict on the idea's merit — say so explicitly, since "deferred" ideas can be revisited later with a different founder, more evidence, or after the current candidates are exhausted.
- **Reject** — reserved for a concrete, checkable hard constraint (e.g., requires a license this founder cannot plausibly obtain, capital requirement far outside any realistic range, direct legal prohibition). Name the specific constraint; "seems unlikely to work" is not a reject-level reason at triage — that judgment belongs in Stage 3, with evidence.

**Cap the candidates receiving "advance to deep evaluation" at 2–3.** If more than 3 clear triage, ask the founder to rank or force a cut rather than deep-diving all of them — bloated parallel deep-dives on 5+ ideas produce repetitive, lower-quality output and a worse decision, not a better one. A forced cut at this stage should default to "defer," not "reject," unless a genuine hard constraint applies.

If two triaged candidates turn out to be the same idea from different angles, merge them before Stage 3. Don't force a merge that papers over a real difference in buyer, mechanism, or GTM motion, and don't keep two framings of one idea distinct past this point either.

### Stage 3 — Deep evaluation (capped candidates only): Friedman's framework

For each of the 2–3 candidates that survived triage, run the full framework from `references/friedman-framework.md`: the 4 common mistakes and the 10 evaluation questions. **This has a required output format — prose alone is not sufficient, because a prose requirement is easy to skip under conversational momentum.** Produce, per candidate:

**A distinct four-mistakes block, before the ten-question table:**
| Mistake | Applies? | Evidence/Inference/Assumption + source | Confidence | Next test |
|---|---|---|---|---|
| Solution in search of a problem | | | | |
| Tar-pit idea | | | | |
| Wrong point on pick-vs-wait spectrum | | | | |
| Abstract, not tractable | | | | |

**Then the ten-question table, all ten rows spelled out — do not collapse rows with "...":**
| # | Question | Verdict | Evidence/Inference/Assumption + source | Confidence | Next test |
|---|---|---|---|---|---|
| 1 | Founder-market fit | | | | |
| 2 | Market size | | | | |
| 3 | Problem acuity | | | | |
| 4 | Competition | | | | |
| 5 | Personal desire | | | | |
| 6 | Why now | | | | |
| 7 | Proxies | | | | |
| 8 | Long-term interest | | | | |
| 9 | Scalability | | | | |
| 10 | Idea-space quality | | | | |

Every row in both tables needs the evidence-type label, its source (a quote from the founder, a search result, or "none — assumption"), and a Next test entry — "none needed" is an acceptable Next test value for a row with high-confidence [Evidence], but the column itself must be filled, not omitted. These tables are the mechanism that actually enforces the evidence-labeling discipline; without them, labels tend to get applied inconsistently or dropped once the conversation is flowing.

**Thresholds, applied after both tables are complete:**
- **Kill** — fails 3 or more of the 10 questions at [Evidence]- or strong-[Inference]-level (not just Assumption-level), *or* fails founder-market fit and scalability simultaneously (these two compound badly). This is an evidentiary verdict, distinct from a Stage 2 "defer" or "reject."
- **Hold / insufficient evidence** — fails 1–2 questions and **no credible fix is identifiable yet** (distinct from the next category, where a fix *is* identifiable). Don't force this into either a clean advance or a kill — name the specific unresolved question(s) and route to the single decisive test that would resolve it, per the output schema below, rather than proceeding on a guess.
- **Advance with a named condition** — fails 1–2 questions but a concrete fix is identifiable now (go to Stage 4).
- **Advance clean** — passes 8+ *and* has no remaining load-bearing assumption at [Assumption]- or weak-[Inference]-confidence. A load-bearing assumption is one that, if wrong, would flip the verdict on founder-market fit, market size, acuity, or scalability specifically — not a minor or peripheral unknown. If such an assumption exists anywhere in the table, the candidate is "hold," not "advance clean," even if it technically passed 8 or more rows — 8 passes plus one unresolved load-bearing assumption is a hold, not a clean advance, because the assumption could still invalidate the whole thesis. Still run Stage 5 after a genuine advance-clean; a clean framework pass does not mean the mechanism works.

Actively look for reasons an idea fails, not just reasons it succeeds — if you notice building a case *for* an idea the founder seems attached to, deliberately construct the counter-case too and show both.

Two questions deserve extra scrutiny because they're the easiest to fudge:
- **Founder-market fit** — distinguish genuine fit ("built this exact system professionally") from mere adjacency ("worked near this problem"), and score adjacency honestly as weaker, labeled.
- **Scalability** — don't default to "pure software passes automatically" (see the corrected guidance in `references/friedman-framework.md`); integration-heavy, support-dependent, or low-retention software can fail this badly even while technically being "software."

### Stage 4 — Reframe, with a kill rule

When an idea is killed, held, or advances-with-a-condition on tar-pit or structural grounds, ask whether a reframe genuinely dissolves the problem before discarding the idea. But apply this rule strictly:

**Reframe only if you can name a concrete new unlock** — a specific technology, regulation, distribution channel, or buyer change that removes the mechanism (not just relabels the product). **Kill the idea (don't reframe) if the structural constraint either remains unchanged or has merely moved downstream** — e.g., "we solved who maintains the data by making agents the consumer" is not a real fix if the new version just recreates the same problem one layer down as "who ensures detection accuracy." A reframe that only sounds different, with the hard problem still present under a new name, is worse than a rejection, because it manufactures false confidence. When in doubt, label the reframe's core claim as [Assumption] and demand a [Next test] before treating it as resolved.

If a reframe genuinely passes this test, re-run it through Stage 3 from scratch — a reframe can fix one flaw while introducing a new one.

See `references/stress-test-patterns.md` for reframe patterns and worked examples, clearly labeled as session-derived rather than part of Friedman's original material.

### Stage 5 — Stress-test the mechanism (route by idea type)

Once an idea survives Stages 3–4, look for the specific mechanism-level flaw a founder would otherwise discover the hard way. **Before picking which failure modes to probe, route by what kind of idea this actually is** — don't default to the enterprise/agent/privacy/platform patterns unless the idea is actually in that category. `references/stress-test-patterns.md` opens with a routing table; consult it first. Failure modes to consider include, depending on fit: trust/autonomy sequencing, privacy/inference leaks, precision/alert-fatigue economics, incentive-compatibility, buyer/owner ambiguity, distribution and CAC, switching costs and retention, unit economics, integration/onboarding burden, marketplace liquidity (two-sided businesses), and raw technical feasibility.

When you find a real flaw, try to resolve it architecturally and name the residual risk honestly — "here's the flaw, here's a design that addresses the core version, here's what's still unresolved" beats either silence or an open objection. Label speculative parts of any proposed fix as [Inference]/[Assumption] with a next test, same as everywhere else.

### Stage 6 — Read insider signal correctly, and protect it

If the founder shares direct, non-public field knowledge (e.g., "I know how [company] is building this internally"), two things apply simultaneously:

**Confidentiality rule:** treat it as a directional hypothesis for reasoning purposes only. Do not restate specific non-public details back at the founder more precisely than they gave them, don't elaborate invented specifics on top of it, and never present it as if it were public market evidence in any output document — label it plainly as non-public/insider information in any thesis document produced, distinct from search-sourced claims.

**Reading discipline:** don't collapse it into one conclusion. Separate the validation reading (confirms the problem is real), the disqualification reading (that specific sophisticated player likely isn't a reachable buyer), and the market-timing reading (an advanced in-house build sometimes previews a requirement that propagates down-market later). **Treat the market-timing reading as a hypothesis requiring its own evidence — timing, buyer, and propagation mechanism — not a default inference just because it produces a satisfying narrative.** It's a known historical pattern in some infrastructure categories, but pattern-matching to it without checking whether the mechanism actually applies here is exactly the kind of confident-sounding-but-unverified claim this skill needs to avoid. Label it [Inference] or [Assumption] and name what evidence (analyst reports, regulatory timelines, comparable company histories) would firm it up.

### Stage 7 — Decide sequencing: wedge vs. platform (if applicable)

Only relevant if the idea has both a narrow sellable application and a larger platform ambition. Apply a cold-start test: can the platform be sold before the market broadly believes the underlying pain is real? If not, sequence the application first as proof and funding, with the platform as an explicit later expansion — state what ships first, what it's meant to prove, and what specifically it unlocks next, rather than asserting the sequencing as obviously correct.

### Stage 8 — Design discovery as one rung on an evidence ladder, not the finish line

Per Friedman, the only fully reliable test is launching — discovery interviews are the cheap approximation, not a substitute for it. Build, per `references/discovery-design.md`:
- An interview script (past/present behavior focus, no pitching until a reaction section).
- A scoring rubric with a **pre-committed decision rule**, written before interviews happen.
- A prospect list if relevant, grounded in a fresh web search, not memory.

**Critical constraint: a positive discovery interview, or even several, should never by itself trigger a "build it" decision.** Frame discovery as the first rungs of an evidence ladder — observed recent behavior (what discovery interviews mostly produce) → access to real artifacts/data confirming the pattern → a warm introduction that converts to a real conversation with a second stakeholder → a design-partner commitment → a paid pilot. Tell the founder explicitly where a given result sits on that ladder, and what the next rung requires, rather than treating "good interviews" as validation.

---

## Output schema (use this for every candidate that reaches Stage 3 or beyond)

Keep this compact — don't restate the full evaluation in prose every time. For each candidate:

**Thesis:** one or two sentences.
**Strongest disconfirming evidence:** the single best reason this might not work, stated as sharply as the strongest reason it might.
**Unresolved assumption:** the load-bearing claim with the least support, labeled per the evidence discipline above.
**Cheapest decisive test:** the next concrete action that would most change confidence, one level up the evidence ladder.
**Verdict:** kill / hold-insufficient-evidence / advance-with-condition / advance clean, matching Stage 3's thresholds.

## Output artifacts (for longer sessions producing saved documents)

1. A **thesis document** — the reasoning chain including rejected branches and why, with evidence labels preserved (not flattened into confident prose during write-up).
2. A **discovery package** — script(s), rubric, decision rule, prospect list if applicable.
3. Optionally, **research notes** with sources and freshness caveats.

Keep these as separate documents — founders return to each for different purposes at different times.

## Tone calibration

Direct, not hedge-everything — but the directness should track calibrated confidence, not narrative confidence. "This fails founder-market fit at [Evidence]-level; you've stated no connection to this space" is the right register. "This space has always failed because X" when X hasn't been checked this session is not — soften that specific claim to "[Assumption, unverified this session]: this space has a history of failed attempts for reason X; worth confirming" instead. Always pair critique with a constructive next move.