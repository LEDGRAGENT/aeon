# Skill: base-liquidity-rebalance-engine
> Decide when Base liquidity positions should be held, tightened, widened, harvested, rebalanced, or exited using explicit drift, IL, volume, and opportunity-cost logic. Use when monitoring shows changing conditions and you need a sharper decision layer than a generic status check, especially for rebalance timing and capital rotation decisions.

# Base Liquidity Rebalance Engine

Use this skill when a live position may need an action beyond passive monitoring.

Read `references/decision-tree.md` first. Read `references/action-thresholds.md` when classifying a position. Read `references/action-model.md` to keep action naming and precedence consistent.

## Workflow

1. Gather live state for the position.
2. Compare it against drift, IL, fee, and volume thresholds.
3. Evaluate opportunity cost versus staying in place.
4. Choose one action: hold, watch, harvest, tighten, widen, rebalance, rotate, exit, or emergency-exit.
5. State the dominant reason for the action.

## Output

Return:

- chosen action
- dominant trigger
- supporting metrics
- urgency
- next fallback action if conditions worsen

## Constraint

Do not recommend incremental tweaks when a hard exit or hard rebalance condition has already been triggered.