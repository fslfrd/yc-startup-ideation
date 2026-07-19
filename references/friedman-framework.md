# Mechanism-Level Stress-Test Patterns

**Provenance note:** everything in this file is session-derived — extrapolated from working through one specific idea (enterprise agent-context infrastructure for regulated financial services) — not from Friedman's talk (`friedman-framework.md`) or from an independent survey of startup failure modes generally. Treat every pattern below as a candidate lens to try, not an established law, and label conclusions drawn from it accordingly in any thesis write-up.

**This file was originally overfit to that one session.** The first six patterns below (enterprise/agent/trust/privacy/platform) are real and useful, but only for ideas that actually involve agents, cross-system data access, or enterprise trust dynamics. Applying them to a consumer app, a marketplace, or a hardware-adjacent idea will produce irrelevant, box-checking analysis that looks rigorous but isn't. **Always route first.**

## Routing table — pick the patterns that actually fit

| If the idea involves... | Use these patterns |
|---|---|
| An AI/agent acting on someone's behalf, or automating a judgment call | Autonomy-must-be-earned, Precision/alert-fatigue |
| Aggregating or surfacing data across multiple people/teams | Detection-vs-disclosure-authority (privacy/inference leaks) |
| A narrow app plus a bigger infrastructure/platform ambition | Wedge-vs-platform sequencing |
| Compliance, risk, or regulated judgment calls | Detection-infrastructure-vs-liability-bearing-service |
| Non-public insider knowledge about an incumbent | Three-readings check (see SKILL.md Stage 6 for the confidentiality rule — that rule is mandatory, not optional, whenever this applies) |
| **Any idea, regardless of category** — check these by default | Distribution & CAC, Switching costs & retention, Unit economics, Technical feasibility |
| **Any B2B idea specifically** — check these by default | Buyer/owner ambiguity, Incentive-compatibility |
| A product with two+ distinct user groups who need each other (buyers/sellers, riders/drivers, employers/candidates) | Marketplace liquidity |
| A product requiring setup, data migration, or connection to a customer's existing systems | Integration/onboarding burden |
| Consumer products, physical/hardware-adjacent products, or anything outside enterprise software | Skip the enterprise-specific patterns above; rely primarily on the general-purpose set below plus Friedman's framework itself — don't force-fit an agent/privacy lens onto an idea that isn't about agents or privacy |

If none of the specific rows fit, default to the general-purpose set (distribution/CAC, switching costs/retention, unit economics, technical feasibility) plus a plain "does the core mechanism actually work as described" gut check — that combination generalizes reasonably well across idea types, unlike the enterprise-specific patterns.

---

## General-purpose patterns (check by default, regardless of idea type)

### Distribution & CAC
How does this specific idea actually reach its first 100 customers, concretely — not "marketing" as an abstraction, but a nameable channel (existing network, a specific community, paid channels with known unit costs, a viral/referral loop with a specific mechanism, a partnership). If the founder can't name a channel with some specificity, that's a real gap, not a detail to defer. Separately check whether CAC is likely to be recoverable within a reasonable payback window given the price point — a good product with an expensive, undifferentiated acquisition channel can still fail.

### Switching costs & retention
For anything with recurring usage or subscription revenue: what happens after the initial novelty or urgency fades? Is there a structural reason usage continues (data lock-in, workflow embedding, network effects among the customer's own users) or does retention depend entirely on the product staying impressively good forever? Ideas that solve an acute but one-time problem (a specific project, a seasonal need) look like recurring businesses but aren't — flag this explicitly since it's easy to miss when the initial demo is compelling.

### Unit economics
At a rough, back-of-envelope level: does revenue per customer plausibly exceed fully-loaded cost to acquire and serve that customer, at a normal or optimistic price point? This doesn't require a spreadsheet at the ideation stage, but a directional sanity check ("if this costs $X to acquire and delivers $Y/month, does that work within a normal payback window") catches ideas that are attractive as a demo but structurally unprofitable.

### Integration/onboarding burden
For anything that needs to connect to a customer's existing systems, data, or workflow: how much setup work does the *first* successful use require, concretely? A long, bespoke onboarding process is a real cost that compounds across every customer (see the scalability corrections in `friedman-framework.md`) and often kills deals before the product's actual value is ever demonstrated. Ask whether there's a way to show value before full integration is complete.

### Technical feasibility
A plain, non-hand-wavy check: does the core mechanism the idea depends on actually work with current technology, at the accuracy/reliability/cost the business model requires — not "AI can probably do this" as a general claim, but the specific capability this specific idea needs. This is especially important to check explicitly (not assume) for ideas whose core value proposition is a capability at the edge of what current models/technology reliably do.

### Marketplace liquidity (for two-sided ideas specifically)
If the idea depends on two or more distinct groups showing up and finding each other (buyers/sellers, employers/candidates, riders/drivers), the central risk is usually not "will people want this" on either side individually — it's the cold-start problem of getting both sides present at once in a specific enough niche that early matches actually happen. Ask which side is acquired first, why that side would show up before the other side exists, and how thin a starting niche (single city, single vertical, single use case) could still produce real matches. A two-sided idea evaluated as if it only had one side is a common and serious blind spot.

### Buyer/owner ambiguity
For any B2B idea — not just horizontal "everyone" ideas — ask explicitly: who has budget, who has the pain, and who has to say yes, and are these the same person? A huge share of B2B ideas fail not because nobody wants them but because the person who feels the pain most acutely (an individual contributor, an end user) has no purchasing authority, while the person with budget doesn't feel the pain directly enough to prioritize it. Name the specific title of the buyer, not a department or "the company." If the founder can't name a specific role that both feels the pain and controls budget, that's a real gap worth surfacing before deep evaluation proceeds, not a detail to resolve later — it directly affects the acuity and market-size questions in Friedman's framework, since a large "market" with no clear buyer isn't really addressable.

### Incentive-compatibility (ongoing, not just at adoption)
Distinct from the one-time question of whether someone will buy: does the system's *ongoing* accuracy, usefulness, or value depend on someone doing unrewarded maintenance work after initial adoption — updating data, correcting outputs, flagging errors, keeping a process current — with no direct personal benefit to them for doing it? This is the specific mechanism behind many tar pits (see the tar-pit-rescue pattern above) and is worth checking even for ideas that pass Friedman's framework cleanly and aren't obviously "knowledge management" in disguise. A useful test: name the specific person who does the maintenance work day-to-day, and ask what they personally get out of doing it well versus doing it adequately or not at all. If the honest answer is "nothing in particular," the system's quality will degrade over time regardless of how good the initial product is — flag this even when it doesn't kill the idea outright, since it usually means the product needs a specific design answer (automating the maintenance, tying it to something the maintainer already wants, or changing who does it) rather than just noting it as a risk.

---

## Patterns specific to agent/enterprise/trust-heavy ideas

Use only when the routing table above indicates fit.

### Pattern: Rescue a tar pit by changing who consumes the output
**Move:** When an idea fails on tar-pit grounds, ask whether the *consumer* of the product's output can change (e.g., a machine/agent instead of a human), which can dissolve incentive-to-maintain problems. **Apply the Stage 4 kill rule strictly here** — this reframe is only valid if the new consumer genuinely removes the maintenance-incentive mechanism, not if it just relocates the same accuracy/maintenance burden to a different name (e.g., "detection accuracy" instead of "human curation effort" — see the Precision pattern below, which is often where a rescued tar pit resurfaces).

### Pattern: Autonomy must be earned, not assumed
**Move:** Any idea involving an AI/agent system acting on someone's behalf needs an explicit answer for how much autonomy it has on day one and how that expands. Propose a graduated ladder (detect → recommend → human-approved action → autonomous action) rather than assuming full autonomy is acceptable from launch, especially for anything customer-facing, financial, or otherwise consequential.

### Pattern: Separate detection authority from disclosure authority
**Move:** For systems aggregating or monitoring across people/teams, check for three concrete leak mechanisms even when individual inputs are correctly permission-filtered: existence disclosure (an aggregate reveals a restricted record exists), differencing attacks (two filtered queries subtract to reveal a restricted record), and derived-evidence leakage (a visible record's underlying evidence isn't visible, but gets smuggled across the boundary via paraphrase). A design pattern that resolves the core version: broad machine-only detection producing structured findings (claim + evidence + provenance), gated through a per-reader disclosure check before any human sees anything, with routing to whoever *is* entitled to act when a reader isn't. Name residual risks (e.g., suppression signaling, timing inference) honestly rather than claiming full resolution.

### Pattern: Detection precision determines whether a monitoring product gets used at all
**Move:** For "surfaces things you should look at" products, check false-positive tolerance explicitly — mediocre precision leads to alert fatigue and quiet abandonment, a slower and easier-to-miss failure mode than outright rejection. Note explicitly that achieving good precision usually requires an accurate baseline of "normal," which can reintroduce whatever hard data problem an earlier reframe was trying to avoid — check for this resurfacing specifically.

### Pattern: Detection infrastructure vs. liability-bearing service
**Move:** For compliance/risk/regulated-judgment ideas, separate a system that renders the judgment and bears accountability for it from one that detects a specific, checkable fact and surfaces it to humans who retain the decision and liability. The first inherits a hard-to-price accountability gap and often becomes a services business despite looking like software; the second is usually a materially easier sell and more scalable.

### Pattern: Reading insider/field signal — the three-readings check
**Move:** See SKILL.md Stage 6 for the full treatment, including the mandatory confidentiality rule. In brief: separate validation (problem is real), disqualification (that specific player isn't a reachable buyer), and market-timing (a down-market propagation hypothesis) — and treat the market-timing reading specifically as a hypothesis needing its own evidence, not a default conclusion, however satisfying the narrative feels.

### Pattern: Wedge-vs-platform sequencing and the cold-start test
**Move:** When an idea has both a narrow sellable application and a platform ambition, check whether the platform can be sold before the market broadly believes the pain is real. If not, sequence the application first as the platform's proof and funding mechanism. Look for a narrower slice of the platform vision that's sellable regardless of the platform's overall adoption timing (e.g., a governance/trust layer sellable to the function currently blocking adoption, independent of how mature end-user adoption is). Address the concentration/trust risk of a platform holding broad access with a concrete architectural answer (e.g., deployment model), not just a policy statement.