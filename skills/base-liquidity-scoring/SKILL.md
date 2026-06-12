# Skill: base-liquidity-scoring
> Score Base chain concentrated liquidity opportunities using LEDGR's deploy threshold, rejection rules, and capital-efficiency framework. Use when evaluating whether a Base pool is deployable, comparing multiple pools, explaining why a pool passed or failed, or converting raw pool metrics like volume, TVL, fee APR, and transaction count into a standardized risk-adjusted score.

# Base Liquidity Scoring

Score pools before discussing deployment.

Use `references/scoring-matrix.md` for the APSM model and `references/scoring-protocol.md` for the broader 100-point scoring framework.

## Workflow

1. Gather raw pool inputs first: pair, TVL, 24h volume, transaction count, fee tier, projected APR, and hook/security notes.
2. Reject immediately if any hard-fail condition is hit.
3. Score the pool against the matrix that best matches the request:
   - Use `references/scoring-matrix.md` for LEDGR's stricter Uniswap V4 deployment screen.
   - Use `references/scoring-protocol.md` for broader Base liquidity ranking and opportunity comparison.
4. State the total score, threshold result, and the 2-4 drivers that mattered most.
5. If the pool passes, suggest the likely strategy archetype to hand off to the operations skill.

## Output format

Return:

- pool or pair name
- total score
- pass/fail against threshold
- kill switch or rejection reason when relevant
- concise rationale by factor
- recommended next action

## Bundled helper

Use `scripts/score-pool.js` to score a pool from JSON input when deterministic scoring is helpful.