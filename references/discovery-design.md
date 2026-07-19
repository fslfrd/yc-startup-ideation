# Discovery Interview Design
 
Use this once an idea has survived the evaluation and stress-test stages (`friedman-framework.md`, `stress-test-patterns.md`) and is ready for real-world validation. The goal of this stage is to design the cheapest test that can actually change the founder's mind — not to produce a polished-looking document.
 
## Core method discipline (Mom Test)
 
- Ask about specific past and present behavior, never hypotheticals, for as long as possible. "Tell me about the last time X happened" beats "would you use a product that does X" every time — people are unreliable narrators of their own hypothetical future behavior but decent narrators of specific past incidents.
- Do not pitch the idea until a dedicated "reaction" section near the end of the interview. Pitching early contaminates everything that follows — people become polite and start looking for ways to be encouraging rather than accurate.
- Compliments are not data. Specifics are data (a dollar figure, a frequency, a name of a tool they tried and abandoned, a quote with a number in it).
- If the person offers to help, sell, or pay before you've asked — that's a strong signal. If they only offer positive reactions when directly prompted, that's a weak one.
## Interview structure template
 
A single 25-30 minute interview should move through:
 
1. **Warm-up (2 min)** — role, team size, current tools/stack. Low-stakes, establishes context, gets them talking.
2. **Context (5-8 min)** — walk me through how [the relevant process] actually works today, end to end. Get them narrating a real workflow, not describing it abstractly.
3. **Deep dive on pain (10-12 min)** — the core of the interview. Ask for specific recent incidents: the last time something went wrong, what it cost, how they found out, how they currently try to prevent it, what they've already tried (bought or built) to fix it and whether it stuck.
4. **Reaction (4-5 min)** — *now* describe the concept, briefly and concretely (a specific scenario, not an abstract pitch). Get their gut reaction, their specific objections, who else would need to approve a purchase, and how they'd want to pay if it worked.
5. **Wrap (2-3 min)** — who else should I talk to, can I follow up with a prototype.
## Designing questions for multiple buyer personas / tracks
 
When a product has more than one stakeholder in the buying or adoption process (e.g., an operational user and a risk/compliance/security approver), build a **separate track per persona** rather than one generic script. Each track should test different things:
- The operational-user track should mostly validate **pain and pull** — is this acute enough, and does the concept generate real interest.
- The approver/gatekeeper track should mostly validate **procurement reality and timing** — what would actually block or unblock a purchase, and whether the underlying pressure (regulatory, competitive, security) is arriving now or later.
Design both tracks so their answers are *comparable* on the same underlying open questions (e.g., both tracks should produce evidence relevant to "which of two candidate wedges has more pull," not just persona-specific trivia).
 
## Scoring rubric and decision rule
 
Before running any interviews, write down:
- **A small set of named signals** you're scoring for (e.g., "pain evidence," "tool gap," "wedge pull," "procurement wall," "timing"), each with a green/yellow/red definition tied to *specific, observable* interview answers (not vibes).
- **An explicit decision rule**, committed to in advance: e.g., "proceed with wedge A if 6 of 10 interviews score green on pain evidence AND wedge pull; if not, but track B shows strong timing signal, reconsider positioning; if both are weak, fall back to alternative wedge B."
Writing the decision rule *before* running interviews is the single most important discipline in this stage — it's specifically designed to prevent the founder (or Claude) from rationalizing weak or mixed signal into a "let's proceed anyway" conclusion after the fact, which is one of the most common and expensive mistakes in early customer discovery.
 
## Prospect / target list research
 
When the founder needs a list of companies or people to reach out to:
 
- **Always ground the list in a fresh web search, not memory.** Market structure (who's still independent, current size rankings, recent M&A, current leadership) changes fast and training data goes stale quickly in exactly this kind of detail — verify before listing.
- **Segment the list** by a variable that matters to the thesis (e.g., company size band, business model, regulatory exposure) rather than producing one flat list — this makes the outreach sequencing decision (who to approach first) much easier and makes the underlying logic auditable.
- **State the selection logic per segment explicitly** (why this size band, why this business model) so the founder can sanity-check or override it — don't just present names.
- **Exclude misfit targets explicitly, with reasons**, especially the most obvious/prestigious names if they don't actually fit the buyer profile (e.g., excluding the largest, most sophisticated players in a market if the thesis specifically depends on those players being unreachable — see the "insider signal" pattern in `stress-test-patterns.md`). Naming and explaining an exclusion is more useful than silently omitting a name the founder will wonder about.
- **Flag data-quality caveats honestly** — note which figures are precise vs. approximate, which sources are more or less reliable (e.g., affiliate/advertiser-supported ranking sites vs. primary regulatory data), and where per-company details (like current leadership names) should be re-verified immediately before outreach rather than trusted from the research pass.
- **Suggest realistic outreach paths**, not just names — warm paths through the founder's own network, relevant industry communities/conferences, and a short, non-salesy cold outreach angle framed around a value exchange (e.g., offering to share anonymized findings back) tend to outperform generic cold outreach for discovery-stage conversations specifically, since the ask is for the person's time and honesty, not a sale.
## Output format
 
Produce a single document per discovery effort containing: the interview script(s) with track separation if applicable, the scoring rubric and decision rule, and the prospect list with segments and sourcing notes — this mirrors how the founder will actually use it (one artifact to work from during the interview sprint), rather than splitting these into separate files.