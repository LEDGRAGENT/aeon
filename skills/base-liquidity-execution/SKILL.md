# Skill: base-liquidity-execution
> Inspect Base liquidity positions, prepare safe transaction payloads, and support execution planning for Uniswap liquidity management without blindly signing or broadcasting. Use when checking existing LP positions, preparing close or rebalance transactions, generating multicall payloads, reviewing execution constraints, or converting a scored liquidity plan into actionable transaction prep.

# Base Liquidity Execution

Use this skill only after a pool or position has already been selected, scored, and approved for execution work.

Read `references/execution-workflow.md` first. Read `references/safety-rules.md` before generating or reviewing any transaction payload.

## Workflow

1. Confirm the target chain, protocol version, wallet, and objective.
2. Inspect the existing position or planned action.
3. Generate transaction payloads or structured execution steps.
4. Verify the payload does not violate capital, IL, or concentration rules.
5. Return the payloads plus a concise operator review summary.

## What this skill is for

- checking wallet balances or rough LP state
- preparing close, collect, or rebalance transaction payloads
- generating multicall calldata for review
- translating a scored plan into execution-ready steps
- reviewing gas, deadlines, and recipient settings before action

## Constraints

- Do not hardcode or expose private keys.
- Prefer payload generation and operator review over blind broadcast.
- Flag protocol-version assumptions explicitly.
- If tooling is incomplete for exact V4 state inspection, say so and limit output to safe preparation steps.

## Bundled helpers

- `scripts/check_lp.js` for basic Base wallet and LP-state inspection
- `scripts/generate_close_tx.js` for close-payload generation on the supported position manager path
- `scripts/close_v3_positions.js` as an operator reminder for safe submission patterns