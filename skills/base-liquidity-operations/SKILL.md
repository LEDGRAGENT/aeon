# Skill: base-liquidity-operations
> Translate scored Base liquidity opportunities into position strategy, allocation, monitoring, and rebalance decisions using LEDGR's Uniswap concentrated liquidity operating rules. Use when a pool already passed initial screening and you need allocation sizing, strategy type, monitoring cadence, rebalance thresholds, harvest rules, or portfolio-level guardrails.

# Base Liquidity Operations

Use this skill after discovery and scoring.

Read `references/core-protocol.md` for operating rules and `references/ceo-charter.md` for macro cadence and escalations.

## Workflow

1. Confirm the pool passed scoring and did not hit a kill switch.
2. Choose the closest strategy archetype from the core protocol.
3. Set provisional allocation, range posture, and monitoring cadence.
4. Check portfolio guardrails before recommending deployment.
5. Define rebalance, harvest, and exit triggers.
6. State the operating plan clearly.

## Output format

Return:

- chosen strategy archetype
- allocation range
- why it fits
- monitoring cadence
- rebalance triggers
- harvest constraints
- exit conditions
- portfolio guardrail notes

## Constraint

Do not recommend deployment that violates capital concentration, max positions, liquidity floor, IL stops, or token concentration rules.