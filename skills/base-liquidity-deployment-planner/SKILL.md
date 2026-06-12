---
name: base-liquidity-deployment-planner
description: Turn approved Base liquidity opportunities into concrete deployment plans with position sizing, reserve treatment, strategy mix, and portfolio-aware allocation logic.
tags: [liquidity, base, planning, allocation]
version: 2.0.0
visibility: public
---

# Base Liquidity Deployment Planner

Use this skill after scoring and before execution.

Read `references/allocation-framework.md` first. Read `references/portfolio-constraints.md` before finalizing any deployment plan.

## Workflow

1. Start from scored pools only.
2. Rank them by capital efficiency and strategic fit.
3. Apply reserve requirements and concentration limits.
4. Allocate capital by strategy type and risk posture.
5. Return a deployment plan with explicit reasons and leftovers.

## Output

Return:

- total deployable capital
- reserve held back
- pool-by-pool allocation
- strategy type per allocation
- why each allocation earned capital
- what was rejected and why

## Constraint

Do not allocate in a way that violates max positions, single-pool concentration, token concentration, or minimum useful deployment size.