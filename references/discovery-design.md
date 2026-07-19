# Discovery Interview Design

**Provenance note:** the interview-discipline principles here (past/present behavior focus, no pitching until late, compliments-aren't-data) are commonly known as "Mom Test" principles, from Rob Fitzpatrick's book *The Mom Test* — not from Friedman's YC talk. The interview structure, rubric, and prospect-research method are session-derived. Keep these attributions separate in any write-up; don't let session-derived process borrow Friedman's or Fitzpatrick's authority by blending voices.

Use this once an idea has survived evaluation and stress-testing (`friedman-framework.md`, `stress-test-patterns.md`). The goal here is to design the cheapest test that can actually change the founder's mind, and to be honest about what that test does and doesn't prove.

## The evidence ladder — read this before running any interviews

Discovery interviews are the *first* rung of a longer ladder, not a validation event on their own. Rank evidence roughly as follows, from weakest to strongest, and always tell the founder which rung a given result sits on:

1. **Observed recent behavior** (what a well-run discovery interview mostly produces) — a specific past incident, its cost, what was tried. Necessary, cheap, but still self-reported and subject to recall bias and social desirability in the room.
2. **Artifact or data access** — the interviewee shares an actual report, dashboard, ticket log, or document confirming the pattern they described, rather than just describing it. Materially stronger than a claim alone.
3. **Warm introduction that converts** — the interviewee introduces you to a second stakeholder (a buyer, an approver, a peer) unprompted or on request, and that conversation happens. Signals real engagement, not just politeness.
4. **Design-partner commitment** — the prospect agrees to a defined, time-bound collaboration with actual obligations on their side: structured feedback on a schedule, early access with a named point of contact, dedicated staff time committed to the pilot, or a defined pilot scope. Strong signal, but still not money — treat it as adjacent to, not equivalent to, rung 5.
5. **Paid pilot** — reserved specifically for a binding commercial commitment: payment changes hands, a signed order form or contract exists, or procurement has issued a formal purchase approval with a dollar amount attached. Don't count "they offered staff time" or "they seemed serious" as rung 5 — that inflates a real but weaker signal (rung 4) into the strongest one, and the gap between "willing to spend their team's time" and "willing to spend money" is exactly the gap this ladder exists to preserve.

**A positive interview alone (rung 1) should never by itself trigger a decision to build.** State explicitly, after any discovery round: which rung the strongest evidence reached, and what the next rung requires concretely. If everything gathered so far sits at rung 1, say so plainly rather than letting a string of enthusiastic conversations read as validation — enthusiasm in an interview room is cheap and well-documented to be a weak predictor of later behavior (this is the entire premise of Mom Test discipline below).

## Core method discipline (Mom Test)

- Ask about specific past and present behavior, never hypotheticals, for as long as possible. "Tell me about the last time X happened" beats "would you use a product that does X."
- Do not pitch the idea until a dedicated "reaction" section near the end. Pitching early contaminates everything that follows.
- Compliments are not data. Specifics are data (a dollar figure, a frequency, a tool they tried and abandoned, a quote with a number in it).
- If the person offers to help or introduce you to someone before being asked, that's rung 3 or 4 happening spontaneously — a strong signal. If they offer to pay unprompted, that's a genuine rung-5 signal, but rare enough at this stage to double-check it's a real commitment and not enthusiasm talking. If they only offer positive reactions when directly prompted, weaker signal, and stays at rung 1 regardless of how enthusiastic it sounds.

## Interview structure template

A single 25-30 minute interview should move through:

1. **Warm-up (2 min)** — role, team size, current tools/stack.
2. **Context (5-8 min)** — walk me through how [the relevant process] actually works today, end to end.
3. **Deep dive on pain (10-12 min)** — the core of the interview. Specific recent incidents, cost, how they found out, what's already been tried and whether it stuck.
4. **Reaction (4-5 min)** — describe the concept briefly and concretely. Get gut reaction, specific objections, who else would need to approve, how they'd want to pay if it worked.
5. **Wrap (2-3 min)** — who else should I talk to, can I follow up.

## Designing questions for multiple buyer personas / tracks

When a product has more than one stakeholder in the buying or adoption process (e.g., an operational user and a risk/compliance/security approver), build a **separate track per persona**. Each track should test different things — an operational-user track mostly validates pain and pull; an approver/gatekeeper track mostly validates procurement reality and timing. Design both tracks so their answers are *comparable* on the same underlying open question, not just persona-specific trivia.

## Scoring rubric and decision rule

Before running any interviews, write down:
- A small set of named signals scored for (e.g., pain evidence, tool gap, wedge pull, procurement wall, timing), each with a green/yellow/red definition tied to specific, observable answers.
- An explicit decision rule, committed to *in advance*: e.g., "proceed with wedge A if N of M interviews score green on pain evidence AND wedge pull." Note explicitly what rung of the evidence ladder this rule is calibrated to (usually rung 1–2) and that clearing it means "proceed to the next rung," not "build."

Writing the decision rule before running interviews is the single most important discipline in this stage — it prevents rationalizing weak or mixed signal into "proceed anyway" after the fact.

## Prospect / target list research

- Ground the list in a fresh web search, not memory — market structure changes fast and training data goes stale quickly in exactly this kind of detail.
- Segment the list by a variable that matters to the thesis, with the selection logic per segment stated explicitly.
- Exclude misfit targets explicitly, with reasons, especially prestigious names that don't fit the actual buyer profile.
- Flag data-quality caveats honestly — precise vs. approximate figures, source reliability, and which details need re-verification immediately before outreach.
- Suggest realistic outreach paths: warm network paths, relevant industry communities, and a short, non-salesy cold outreach angle framed around a value exchange.

## Output format

Produce a single document per discovery effort: interview script(s) with track separation if applicable, the scoring rubric and decision rule (with its evidence-ladder rung noted), and the prospect list with segments and sourcing notes.