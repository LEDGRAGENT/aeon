# Skill: base-liquidity-scanner
> Scan Base chain liquidity opportunities for high-yield concentrated liquidity candidates, rank pools for further review, and prepare shortlist inputs for LEDGR scoring. Use when asked to scan Base for high-yield pools, discover opportunities, rank candidate pairs, screen pools before deployment, or prepare raw metrics for a concentrated liquidity decision.

# Base Liquidity Scanner

Use this shortlist skill to turn pool data into a ranked shortlist for scoring.

Read `references/discovery-workflow.md` before scanning. Use `references/metrics-checklist.md` to ensure the shortlist includes the right fields for handoff into scoring.

## Workflow

1. Identify the candidate universe on Base.
2. Gather comparable metrics for each candidate pool.
3. Normalize the fields needed by the scoring skill.
4. Remove obvious low-quality pools before deep review.
5. Produce a shortlist ranked by likely capital efficiency.
6. Hand shortlisted pools to the scoring skill for threshold evaluation.

## Required shortlist fields

For each pool, collect:

- pair / symbols
- protocol / venue
- TVL
- 24h volume
- volume-to-liquidity ratio
- transaction count if available
- fee tier
- projected or trailing APR if available
- hook / custom logic notes if relevant
- why it is worth scoring

## Output

Return a ranked shortlist, not a deployment order. Scanning is discovery. Scoring decides deployability.