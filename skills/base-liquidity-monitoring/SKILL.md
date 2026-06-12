# Skill: base-liquidity-monitoring
> Monitor Base concentrated liquidity positions for drift, IL risk, volume collapse, rebalance conditions, and harvest timing using LEDGR's operating thresholds. Use when checking active positions, deciding whether a position should be watched, rebalanced, harvested, or exited, building heartbeat monitoring routines, or converting operating rules into an ongoing surveillance checklist.

# Base Liquidity Monitoring

Use this skill after positions exist or when designing a monitoring loop for Base liquidity.

Read `references/monitoring-cycle.md` first. Read `references/rebalance-triggers.md` when evaluating whether an alert should become an action. Read `references/state-persistence.md` when maintaining continuity across review cycles. Read `references/position-types.md` when structuring position records and status outputs.

## Workflow

1. Identify the positions or pools being monitored.
2. Gather current price drift, IL estimate, fee accrual, and recent volume context.
3. Compare the current state against heartbeat and rebalance thresholds.
4. Classify each position as hold, watch, harvest, rebalance, or exit.
5. Return the decision with the threshold that triggered it.

## Output format

Return for each position:

- status: hold, watch, harvest, tighten, widen, rebalance, rotate, exit, or emergency-exit
- key metric snapshot
- exact trigger hit
- urgency level
- next review cadence

## Constraint

Do not recommend passive continuation when hard stop conditions are already breached.

## Bundled helper artifacts

- `scripts/monitoring-checklist.md`
- `scripts/heartbeat-template.md`
- `scripts/portfolio-state-template.json`
- `scripts/update-portfolio-state.js`

base-liquidity-skills — gitlawb