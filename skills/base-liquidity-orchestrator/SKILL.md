# Skill: base-liquidity-orchestrator
> Orchestrate the full Base concentrated liquidity workflow by deciding when to use scanning, scoring, operations, execution, and monitoring skills. Use when a request spans multiple stages of the liquidity lifecycle, such as finding pools and deciding deployment, reviewing an existing position portfolio, or managing an opportunity from discovery through monitoring.

# Base Liquidity Orchestrator

Use this skill when the request is multi-stage or ambiguous about which liquidity sub-skill should be applied first.

Read `references/workflow-map.md` first.

## Stage routing

- Use `base-liquidity-scanner` for discovery and raw shortlist creation.
- Use `base-liquidity-scoring` to determine pass/fail and compare opportunities.
- Use `base-liquidity-operations` to convert scored pools into strategy and allocation plans.
- Use `base-liquidity-execution` to inspect positions or prepare transaction payloads.
- Use `base-liquidity-monitoring` for live position surveillance, rebalance logic, and heartbeat review.

## Default order

1. discovery
2. scoring
3. operations planning
4. execution prep
5. monitoring

## Rules

- Do not skip scoring before proposing deployment.
- Do not skip operations planning before execution prep.
- Do not present execution payloads as completed actions.
- If the user only wants one stage, stay within that stage.
- If data is missing, stop at the highest-confidence stage and say what is still needed.