# Skill: base-liquidity-data-adapters
> Normalize and prepare raw Base liquidity market data from multiple sources for downstream scanning and scoring. Use when pool data comes from mixed APIs, explorers, subgraphs, dashboards, or manual exports and needs to be cleaned into a consistent shape with TVL, volume, fee tier, transaction count, routing rank, and structural risk fields.

# Base Liquidity Data Adapters

Use this skill before scanning when raw market data is messy, partial, or source-specific.

Read `references/canonical-schema.md` first. Read `references/source-normalization.md` when merging data from multiple providers. Read `references/live-source-notes.md` when ingesting fresh public market snapshots.

## Workflow

1. Identify the source format.
2. Map source fields into the canonical pool schema.
3. Compute derived fields like volume-to-liquidity ratio.
4. Preserve uncertainty notes when fields are approximate or missing.
5. Output normalized records for the scanner and scorer.

## Output

Return normalized pool objects with:

- pair
- venue
- TVL
- 24h volume
- volume/liquidity ratio
- tx count
- fee tier
- projected APR if available
- routing rank if available
- hook risk note
- source confidence note

## Bundled helpers

- Use `scripts/normalize-pool-data.js` to convert raw JSON arrays into the canonical schema.
- Use `scripts/fetch-dexscreener-token.js` for fast token-level live market snapshots.
- Use `scripts/fetch-dexscreener-pair.js` for direct pair-level live market snapshots.