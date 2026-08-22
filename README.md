# aave-v3-base

A [nuthatch](https://github.com/nightswatchhq/nuthatch) nest: **Aave V3 on Base**.

As `aave-v3`, re-pointed at Base.

One binary, one config file, no graph-node, no gateway, no query fees.

## What it indexes

**Chain:** `base`. **1 contract**, **15 tables**.

| alias | address |
|---|---|
| `c0` | `0xa238dd80c259a72e81d7e4664a9801593f98d1c5` |

## Verified

Indexed blocks **50,015,570 to 50,314,928** and sealed **122,749 events**. Every table below is generated from the vendored ABIs, and the run above is what this nest actually decoded, not an estimate.

## Read this before trusting it

- Event set is **identical** to the Ethereum deployment's, despite different implementation bytecode.

## Run it

```sh
nuthatch init --from https://github.com/nightswatchhq/aave-v3-base
cd aave-v3-base
nuthatch dev --dir . --backfill 50000 --seal-direct
nuthatch sql --dir . "SELECT count(*) FROM \"c0__borrow\""
```

The endpoint in `nuthatch.toml` is keyless and public, so this file is publishable: a `nuthatch.toml` is pinned into the nest's content address and must never carry a credential. It is enough to follow the tip. A **backfill** wants archive depth it may not have: pass your own with `--rpc`, and check it first with `nuthatch doctor --rpc <url>`.

## Tables

```
c0__borrow
c0__deficit_covered
c0__deficit_created
c0__flash_loan
c0__liquidation_call
c0__minted_to_treasury
c0__position_manager_approved
c0__position_manager_revoked
c0__repay
c0__reserve_data_updated
c0__reserve_used_as_collateral_disabled
c0__reserve_used_as_collateral_enabled
c0__supply
c0__user_e_mode_set
c0__withdraw
```
