# Reframing and Mechanism-Level Stress-Test Patterns
 
These patterns go beyond Friedman's market-level framework (`friedman-framework.md`) into how an idea actually *works* — the level where founders (and Claude) most often discover fatal flaws only after building. Each pattern below includes the abstract move and the worked example it was distilled from.
 
---
 
## Pattern: Rescue a tar pit by changing who consumes the output
 
**Move:** When an idea fails on tar-pit grounds (Stage 3), don't just discard it — ask specifically whether the *consumer* of the product's output can change. A huge fraction of tar pits fail because they depend on unrewarded human effort (maintaining data, following a process, adopting a habit). If the primary consumer of the output can become a machine/agent instead of a human, the incentive-to-maintain problem frequently dissolves, because the machine's own operation (success/failure signals) becomes the maintenance mechanism.
 
**Worked example:** "Company knowledge management" is a 25-year graveyard (Lotus Notes, SharePoint, enterprise wikis) because employees have no personal incentive to keep a shared knowledge base current. Reframing the same underlying data problem as "context infrastructure that AI agents consume to act" changes the maintenance mechanism: the system stays current because agents are running against it continuously and their failures reveal staleness, not because a human volunteers to update a wiki page.
 
**Caution:** Always re-run the reframed idea through the full framework — a reframe that solves one structural problem often introduces a new one. In the worked example, "agents consuming context and acting" immediately introduced a *new* problem (see next pattern) that the original knowledge-management framing never had to deal with.
 
---
 
## Pattern: Autonomy must be earned, not assumed
 
**Move:** Any idea involving an AI/agent system acting on a company's behalf needs an explicit answer to: how much autonomy does the system have on day one, and how does that expand? "Full autonomy from launch" is almost always wrong for anything with real consequences (customer-facing actions, financial actions, data modification) — not because the technology can't do it, but because trust in enterprise software is earned incrementally, and one bad autonomous action early can kill the relationship regardless of the system's aggregate accuracy.
 
**Design pattern to propose:** a graduated ladder — detect → recommend → human-approved action → autonomous action — where each stage unlocks based on demonstrated accuracy, and the product's headline value proposition should usually live at "found it without being asked," with action requiring one human click, rather than promising full autonomy out of the gate. Detection can and should be autonomous even when action isn't; that split (see next pattern) is usually the resolution.
 
**Worked example:** "Agent that finds problems across the company and fixes them without any human prompt" was refined to "agent that finds problems without being asked, then drafts the fix as a one-click action" — same core value proposition, materially different (and sellable) trust posture. The action safety profile also varies sharply by domain: intra-system fixes (merging duplicate tickets) are lower-risk than customer-facing ones (emailing a customer), which affects how fast the ladder can climb in a given vertical.
 
---
 
## Pattern: Separate detection authority from disclosure authority
 
**Move:** Any system that aggregates or monitors information *across* people or teams (not just working within one person's own permissions) faces an inference-leak problem: even if every individual input is correctly permission-filtered, the aggregate *output* (a count, a rollup, a cross-referenced insight) can reveal more than any single input was allowed to disclose. This is a big-enough trap that it deserves explicit checking any time a product's value depends on org-wide (not just per-user) visibility.
 
**The three concrete leak mechanisms to check for:**
1. **Existence disclosure** — an aggregate count or summary reveals that a restricted record exists, even though its contents stay hidden.
2. **Differencing attacks** — two filtered queries, subtracted, reveal information about a specific restricted record neither query showed directly.
3. **Derived-evidence leakage** — the record itself is visible to the reader, but the *evidence* behind a claim about it (a private message, a restricted document) isn't, and the system's output smuggles that evidence across the permission boundary via paraphrase or summary.
**Design pattern to propose:** split the system into two roles. A broad, machine-only **detection** layer can read everything (never surfaces raw content to a human directly) and produces structured findings (a claim + its evidence set + full provenance). A separate **disclosure gate** then checks each finding against each specific reader's actual entitlements before anything is shown to them, with three possible outcomes: full disclosure (reader is entitled to all the evidence), tiered disclosure (the claim is shown, but evidence is downgraded to a level the reader may see — e.g., "no reply in 14 days" instead of quoting the private message), or routing (the reader isn't entitled to any of it, so the finding routes instead to whoever *is* entitled to act on it, often with an escalation timer). This converts a privacy constraint into a product feature (problems get routed to whoever can actually act, and chased) rather than a limitation.
 
**Residual risk to name honestly, not hide:** this pattern doesn't solve everything. Suppression signaling (a suspiciously sparse rollup can itself hint that something's being withheld) and timing inference (observing someone act can imply a finding existed) usually remain as small, generally-acceptable residual risks — say so explicitly rather than claiming a fully solved problem.
 
---
 
## Pattern: Detection precision determines whether a monitoring product gets used at all
 
**Move:** For any product whose core value is "surfaces things you should look at" (as opposed to doing the work directly), check false-positive tolerance explicitly. Buyers stop reading alerts within weeks if precision is mediocre — this has killed a specific, nameable pattern across product categories (observability tooling, sales-intelligence "insights" tabs that go unread, RPA hitting a wall). The failure mode is not "the product doesn't work," it's "the product works badly enough, badly enough of the time, that humans learn to ignore it" — a slower, quieter death than an outright rejection.
 
**Implication:** precision requires an accurate baseline of "what's normal," which usually re-couples the idea back to whatever hard data-modeling problem an earlier reframe was trying to avoid (see first pattern above — the tar pit has a way of resurfacing one layer down). Don't treat a reframe as having eliminated a hard problem if it's actually just relocated it to a "detection accuracy" requirement.
 
---
 
## Pattern: Detection infrastructure vs. liability-bearing service — a critical distinction
 
**Move:** When evaluating any idea that touches compliance, risk, or regulated judgment calls, explicitly separate two very different postures: (a) a system that *renders the judgment itself* and bears accountability for it (e.g., "we determine whether this transaction is suspicious"), versus (b) a system that *detects a specific, checkable fact and surfaces it to the humans who retain the decision and liability* (e.g., "this ID expired," "this document is missing," "this file has been untouched for nine days"). Posture (a) inherits an accountability gap that's very hard to price or insure around as a startup (who signs the attestation when the AI misses something?) and often collapses into a human-labor-heavy services business despite looking like software (see Friedman question 9). Posture (b) is a materially easier sell and a materially more scalable business, because the customer keeps the liability and the decision — the product just makes the gap impossible to miss.
 
**Worked example:** "AI-native compliance service that does the compliance work" was rejected on exactly this basis; "detection infrastructure that flags missing/expired KYC documents inside the client's own workflow" was accepted, because it's structurally the same underlying domain but a different posture toward liability.
 
---
 
## Pattern: Reading insider/field signal — the three-readings check
 
**Move:** When a founder reports direct, non-public knowledge that a sophisticated incumbent is already solving this problem in-house, resist collapsing that into a single conclusion. Explicitly separate:
1. **Validation** — sophisticated, well-resourced players investing real effort confirms the underlying problem is genuine and urgent, not imagined.
2. **Disqualification** — it usually also means that *specific* sophisticated player is not a reachable near-term customer; they'll build rather than buy, for capability, control, and often regulatory-ownership reasons.
3. **Market-timing / category-formation signal** — frequently the most valuable and least obvious reading: an advanced player's in-house build often previews a requirement that will propagate down-market over the following 1-3 years (via regulatory expectation, competitive pressure, or simple imitation) to players who lack the resources to build it themselves. This is a well-established historical pattern in infrastructure categories — sophisticated-user-builds-in-house, followed by an independent vendor winning the rest of the market once the requirement is proven and standardized. Pattern-match to known examples if it genuinely fits, but don't force the analogy onto a case where the underlying dynamics differ.
**Implication to draw out explicitly:** this reading often flips the go-to-market target away from the sophisticated player the founder has visibility into, toward the *less-resourced followers* who will face the same requirement later without the capability to build it — and toward selling infrastructure that's ready when that requirement hits. Walk the founder through this flip as reasoning, not just a stated conclusion, since it's usually counterintuitive on first hearing ("wait, so my insider knowledge of Company X means I shouldn't sell to Company X?").
 
---
 
## Pattern: Wedge-vs-platform sequencing and the cold-start test
 
**Move:** When an idea has both a narrow, immediately-sellable application and a larger infrastructural/platform ambition, resist defaulting to pitching the platform. Apply a cold-start test: can the platform be sold and adopted *before* the market broadly believes the underlying pain is real and urgent? Platforms and control-plane-style infrastructure (the "Okta/Kafka/Snowflake" pattern — a neutral layer other systems come to depend on) are usually two-sided and suffer acute chicken-and-egg problems pre-adoption: no customers without integrations, no integrations without customers.
 
**Design pattern to propose:** the narrow application is the platform's proof and funding mechanism, not a distraction from it — ship the application first, prove the underlying infrastructure works and generates revenue on a sellable cycle, then expose the infrastructure (APIs, integration points) to expand toward the platform position once the application has established trust and a customer base. This mirrors well-known historical sequencing (a company running its own operations on infrastructure before selling that infrastructure to others).
 
**Companion move — find the wedge inside the platform vision that's sellable today regardless of timing risk.** Often a platform ambition contains a narrower slice that solves a problem which exists *right now*, independent of how mature the broader vision's adoption curve is (e.g., inside a "let agents access enterprise systems" platform vision, "let security teams govern and audit the agents already being deployed today" is a wedge sellable immediately, because the governance pain doesn't wait for full agent adoption — it exists at every point on that curve). Look for this kind of time-independent wedge specifically; it de-risks the platform's biggest weakness (uncertain adoption timing).
 
**Also address directly, not implicitly:** a platform holding broad cross-system access is a bigger security target than a narrow application — this needs an explicit architectural answer (e.g., in-customer-tenant/VPC deployment so sensitive data never leaves the customer's own environment), not just a policy promise.