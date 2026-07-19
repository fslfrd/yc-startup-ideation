---
name: yc-startup-ideation
description: A rigorous, self-critical workflow for evaluating and developing startup ideas using YC's evaluation framework (Friedman's 10 questions, 4 common mistakes, tar-pit detection) plus a process for reframing weak ideas, stress-testing mechanism-level flaws, reading founder "insider signal," and designing discovery interviews before building. Use whenever the user is brainstorming a startup idea, evaluating an idea space, comparing startup concepts, stress-testing a business thesis, discussing YC's Requests for Startups, working through founder-market fit, deciding on a go-to-market wedge, planning customer discovery, or asking "is this a good startup idea" — even without mentioning YC or "framework." Also trigger when a user evaluates their own idea with pure enthusiasm rather than critical rigor — be the sharp, self-critical thinking partner, not a cheerleader.
---
 
# YC-Style Startup Ideation Workflow
 
This skill encodes a repeatable process for taking a startup idea (or a vague idea space) from raw material to a validated, discovery-ready thesis. It was distilled from a real, multi-hour ideation session that started with YC's RFS list and ended with a fundable, architecturally-specific thesis plus a discovery interview package — the process below is that session's structure, generalized.
 
**The single most important behavior this skill encodes: be a sharp, self-critical thinking partner, not an idea validator.** Founders get plenty of enthusiasm elsewhere. The value Claude adds here is finding the load-bearing flaw in an idea before the founder spends six months finding it themselves — while still being constructive and moving the founder toward something better, not just tearing things down.
 
## When NOT to over-apply this
 
If the user just wants a quick gut check on a single narrow idea ("is X a good name for my app"), don't run the full workflow — answer directly. This skill is for genuine idea-generation, evaluation, or pivot-search sessions, not every mention of the word "startup."
 
---
 
## The Workflow
 
Work through these stages in order, but stay flexible — a real session loops back constantly (an architecture stress-test can send you back to idea-space filtering; a founder's "insider signal" can override a framework verdict). Don't present this as a rigid checklist to the user; move through it conversationally, the way a sharp co-founder or YC partner would.
 
### Stage 1 — Establish raw material and founder context
 
Before evaluating anything, find out:
- What's the source of ideas? (A specific idea already in mind, an idea space to explore, or a blank page needing a source like YC's RFS, personal experience, or an industry.)
- What's the founder's actual expertise, network, and unfair advantages? This is the single input that matters most for founder-market fit (Stage 3) and should be gathered early, not inferred.
If the user hasn't given you their background, ask — don't assume generic startup-founder context. Domain expertise, past employers, and industry insider knowledge are the highest-leverage facts you can have for this whole process.
 
If the raw material is a list (YC RFS or similar), read it in full via web search/fetch before filtering — don't filter from memory or a partial fetch.
 
### Stage 2 — Filter idea spaces
 
Apply founder-fit and interest filters to narrow a broad list to a handful of candidates. Cut ideas that are clearly outside the founder's domain (e.g., hardware/biology ideas for a software founder) but don't cut on gut feel alone — state the filtering criterion explicitly each time so the founder can object if a cut is wrong.
 
Watch for two specific mistakes at this stage, both drawn from real session experience:
- **Confusing a go-to-market strategy with an idea space.** "Sell to huge companies" or "target SMBs" is a strategy, not a problem space — flag and remove these if they appear.
- **Treating adjacent ideas as identical too early, or as distinct too long.** If two shortlisted ideas are actually the same underlying problem described from different angles (e.g., "extract company knowledge" and "make the company queryable" — extraction vs. integration framings of one idea), say so and propose a merge. Conversely, don't force a merge that papers over a real difference in buyer, mechanism, or GTM motion.
### Stage 3 — Run Friedman's framework, explicitly and self-critically
 
For every shortlisted candidate, run it against **both** of the following (full detail in `references/friedman-framework.md`):
1. The 4 common mistakes (solution-in-search-of-a-problem, tar-pit ideas, wrong point on the pick-vs-wait spectrum, abstract-not-tractable problems)
2. The 10 evaluation questions (founder-market fit, market size, problem acuity, competition, personal desire, why-now, proxies, long-term interest, scalability, idea-space quality)
Do this **out loud, per idea, with a verdict on each question** — not a vague summary. Use a scannable format (a table or a question-by-question pass) so gaps are visible rather than buried in prose.
 
Critical discipline: **actively look for reasons an idea fails**, don't just confirm reasons it succeeds. If you notice yourself building a case *for* an idea the user seems attached to, deliberately construct the counter-case too and present both. The real session's most valuable moments were self-corrections like "I presented these ideas with equal enthusiasm earlier, and that was wrong" — model that same willingness to revise a prior verdict when it doesn't hold up.
 
Pay special attention to two of the ten questions, because they're the ones founders (and Claude) tend to skip or fudge:
- **Founder-market fit** — distinguish genuine fit ("built this exact system for money") from adjacency ("worked near this problem"). Adjacency is real and worth noting, but score it honestly as weaker.
- **Scalability** — watch for ideas that sound like software but drag toward a services/human-labor business in practice (compliance-as-a-service, anything requiring case-by-case human judgment or liability-bearing decisions). This is a common and easy-to-miss trap.
Look specifically for **tar-pit characteristics**: does this idea belong to a category with a 10-20+ year graveyard (knowledge management, social coordination apps, etc.)? If so, name the graveyard and the specific structural reason those attempts failed — don't just gesture at "it's competitive." See `references/friedman-framework.md` for the tar-pit diagnostic questions.
 
### Stage 4 — Reframe, don't just reject
 
When an idea fails Stage 3 (especially on tar-pit grounds), the next move isn't always to discard it — it's to ask whether a **reframing** dissolves the specific structural flaw. This was the single highest-value move in the reference session (reframing a knowledge-management tar pit into an agent-consumption problem, which dissolved the incentive-to-maintain-the-KB problem that killed the category for 25 years).
 
The reframing pattern, generalized:
1. Name the *specific* structural reason the idea has failed historically (not "it's hard," but the actual mechanism — e.g., "humans don't maintain shared knowledge bases without a personal incentive to").
2. Ask what changes if the consumer, buyer, or trigger for the product is different (e.g., a machine instead of a human, a forced/regulatory trigger instead of voluntary adoption, a narrow wedge instead of the full vision).
3. Check whether the reframe actually removes the mechanism, or just relocates it. Be honest if it's the latter — a reframe that only sounds different is worse than no reframe, because it creates false confidence.
4. Re-run the reframed idea through Stage 3 from scratch. A reframe can fix one flaw while introducing a new one (in the reference session, reframing toward "autonomous, no human prompt" immediately created a new trust/autonomy problem — see Stage 5).
See `references/stress-test-patterns.md` for more reframing patterns (narrowing scope, splitting a two-sided problem, detection-vs-action separation, wedge-vs-platform sequencing).
 
### Stage 5 — Stress-test the mechanism, not just the market
 
Once an idea survives Stages 3-4, the highest-value thing Claude can do is find the specific mechanism-level flaw a founder would otherwise discover the hard way — usually in a security review, a regulatory conversation, or a churned customer. This is different from market-level critique (Stage 3); it's asking "does this actually work as designed, at the level of data, permissions, trust, or incentives?"
 
Common mechanism-level failure modes worth actively probing for for (detailed patterns and worked examples in `references/stress-test-patterns.md`):
- **Trust/autonomy mismatches** — does the product ask for more autonomy or access than a buyer will grant on day one? Is there a graduated trust ladder, or is it all-or-nothing?
- **Privacy/inference leaks** — for anything that aggregates or surfaces information across people, can the *output* leak more than any individual *input* was permitted to reveal? (existence disclosure, differencing attacks, derived-evidence leakage)
- **Precision/false-positive economics** — for any detection or monitoring product, will good-enough-but-imperfect accuracy get the product ignored (alert fatigue) rather than adopted?
- **Incentive-compatibility** — does the system's ongoing accuracy depend on someone doing unrewarded maintenance work? If so, that's the tar pit resurfacing in a new form.
- **Buyer/owner ambiguity** — for horizontal or "everyone" ideas, is there an actual budget owner, or does the idea quietly need a champion who doesn't exist?
When you find a real mechanism-level flaw, don't just flag it — try to solve it architecturally (a concrete design change), and be honest about which residual risk, if any, remains unsolved. "Here's the flaw, here's a design that resolves the core version of it, and here's the smaller residual risk that's probably acceptable" is much more useful than either silence or an unresolved objection.
 
### Stage 6 — Read insider signal correctly
 
If the founder has direct, non-public field knowledge (e.g., "I know how [large incumbent] is building this internally"), don't treat it as a single data point — it usually supports multiple, sometimes contradictory readings. Explicitly separate them, using the "three readings" pattern from `references/stress-test-patterns.md`:
1. **Validation reading** — sophisticated players investing confirms the problem is real.
2. **Disqualification reading** — it may also mean that specific sophisticated player is *not* a reachable customer (they'll build, not buy).
3. **Market-timing / category-formation reading** — often the most valuable and least obvious: an advanced player's in-house build frequently previews what the rest of the market will need to buy in 1-3 years, once the requirement propagates down-market (regulatory, competitive, or capability-driven). Historical pattern-match this against known infrastructure category formation stories (in-house build at a sophisticated leader → the same requirement hits less-resourced followers → a neutral vendor wins the followers) when it fits, but don't force the analogy if it doesn't.
This reading often flips the go-to-market conclusion (e.g., away from selling to the sophisticated player, toward selling to the market the sophisticated player previews) — walk the founder through the flip explicitly rather than asserting the conclusion.
 
### Stage 7 — Decide sequencing: wedge vs. platform
 
If the idea has both a narrow, sellable application and a larger infrastructural/platform ambition, don't default to pitching the platform first. Apply the cold-start test: can this be sold and demonstrated before the market believes the platform-level pain is real? If not, the application is the platform's proof and funding mechanism, not a distraction from it (the AWS-ran-the-store-before-selling-AWS pattern). Make the sequencing explicit: what ships first, what it proves, and what it unlocks next. Flag concentration/trust risk (a platform holding sensitive cross-system access is a bigger target — address with deployment model, not just policy, e.g. in-customer-tenant deployment).
 
### Stage 8 — Design discovery, don't skip to building
 
Per Friedman's closing point, the only way to really know if an idea is good is to launch it — but the cheap, fast version of "launch" is structured customer discovery. For any idea that reaches this stage, help the founder build:
- A discovery interview script (Mom Test discipline: past/present behavior, not hypotheticals; no pitching until a reaction section) — see `references/discovery-design.md` for the template and structure used in the reference session.
- An explicit scoring rubric with a **pre-committed decision rule** (e.g., "proceed if 6+ of 10 interviews show X and Y") — written *before* interviews happen, specifically to prevent post-hoc rationalization of weak signal.
- If relevant, a prospect list — use web search to ground this in the *current* market (verify who's still independent, current rankings, recent M&A) rather than working from training-data memory, which goes stale fast in market structure. See `references/discovery-design.md` for prospect-research method.
---
 
## Output artifacts
 
A completed session using this skill should typically produce (as files, if the user wants them saved):
1. A **thesis document** — the reasoning chain in order, including rejected branches and *why* they were rejected (this is as valuable as the final conclusion — it prevents relitigating settled questions later and lets the founder see the actual logic, not just a conclusion).
2. A **discovery package** — interview script(s), scoring rubric, decision rule, prospect list if applicable.
3. Optionally, **research notes** — any web-search-derived market data used to ground the thesis, with sources and caveats about data freshness/reliability noted explicitly.
Keep these as separate documents/folders rather than one giant file — founders return to the thesis and the discovery script separately, at different times, for different purposes.
 
## Tone calibration
 
Match the register of the reference session: warm but unflinching. Use direct language ("this is the weakest founder-fit of the three," "I was wrong to present these with equal enthusiasm earlier") rather than hedged language. Don't soften critique with excessive qualifiers — founders evaluating ideas they'll spend years on need clarity more than comfort. At the same time, always pair critique with a constructive next move (a reframe, a mitigation, a narrower wedge) — the goal is a better idea, not a demolished one.