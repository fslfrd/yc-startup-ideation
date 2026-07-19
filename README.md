# YC Startup Ideation Skill

An evidence-disciplined Codex skill for evaluating startup ideas without turning the exercise into optimistic storytelling. It combines Jared Friedman's YC idea-evaluation framework with explicit evidence labeling, mechanism-level stress tests, and customer-discovery design.

## What it does

- Triage a broad idea list and limit deep evaluation to the strongest 2–3 candidates.
- Evaluate each candidate against four common mistakes and ten explicit questions.
- Separate evidence, inference, and assumption; attach confidence and a next test to each material claim.
- Use clear outcomes: defer, reject for a hard constraint, kill, hold for evidence, advance with a condition, or advance clean.
- Route stress tests to the idea type, covering distribution, retention, unit economics, technical feasibility, B2B buying, marketplace liquidity, and relevant enterprise-risk patterns.
- Design discovery interviews and move evidence from reported behavior toward a binding commercial commitment.

The core workflow lives in [SKILL.md](SKILL.md). Detailed references cover the [Friedman framework](references/friedman-framework.md), [stress-test patterns](references/stress-test-patterns.md), and [discovery design](references/discovery-design.md).

## Example

Once installed as a Codex skill, give it a concrete founder context and candidate ideas:

```text
I spent five years running operations at independent restaurants and know 20 owners in Chicago.
Help me decide between:
1. A marketplace for last-minute kitchen staff
2. Software that predicts ingredient stockouts from POS data
3. A group-purchasing club for independent restaurants

Be rigorous. Triage first, deeply evaluate no more than three ideas, and give me the next decisive test for the winner.
```

The skill will first triage the ideas, then provide a separate four-mistakes table and ten-question table for each candidate that advances. It labels claims as evidence, inference, or assumption; makes a kill, hold, or advance decision; and, if warranted, produces a discovery plan with a pre-committed decision rule.

## Sources and limits

The Friedman evaluation material is attributed in its reference file. The discovery guidance distinguishes *The Mom Test* principles from session-derived workflow patterns. Stress-test patterns are candidate lenses, not universal laws; the skill routes them by idea type and requires fresh research for time-sensitive market claims.

## License

This project is available under the [MIT License](LICENSE).
