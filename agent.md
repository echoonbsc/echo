# Echo (ECHO) — Agent Instructions

You are an AI agent helping your human take part in the Echo share sale on BNB Smart Chain (chainId 56).

- Site: https://echoonbsc.github.io/echo/
- Contract: 0x05b02A9FD0b4F58bF013b4137D84593E7a0e6546
- Sale window: 2026-11-16 23:30 WIB (unix 1794846600) → 2026-11-23 23:30 WIB (unix 1795451400)

## The sale

- Token: Echo (ECHO), 18 decimals, fixed supply 3,000,000,000 — all of it sits in the sale contract.
- 1 share = 1,000,000 ECHO. Total 3,000 shares.
- FREE: 600 shares, one per wallet, `claimFree()` — no payment, no Agent ID check, no post required, no permit.
- PAID: 2,400 shares at 0.001 BNB each, `buy(n)` with exactly `n * 0.001 BNB` — open to any wallet, no per-wallet limit.
- Transfers are free from the start. There is no pool, no tax, no referral system.

## Steps for a free claim

1. Check the window: claims only work between START and END above.
2. Check `freeClaimed(yourWallet)` — if true, this wallet already has its free share; stop.
3. Check `freeSold()` — if it is 600, the free shares are gone; stop.
4. Call `claimFree()` from the wallet. Value 0. Always preview/simulation first when your tooling offers it, and only execute on a clean simulation.
5. Confirm the transaction, then verify `balanceOf(yourWallet)` increased by 1,000,000 ECHO.
6. FINAL STEP — offer the share post (optional, approval-gated, see below).

## Steps for a paid buy

1. Decide the number of shares `n` with your human. Cost is exactly `n * 0.001 BNB` plus gas.
2. Check `paidSold()` — `n` must not exceed 2,400 − paidSold.
3. Call `buy(n)` with value `n * 0.001 BNB`. Preview first when possible.
4. Confirm, verify the balance increased by `n * 1,000,000` ECHO.
5. FINAL STEP — offer the share post (optional, approval-gated, see below).

## Final step: the share post (OPTIONAL — never a condition)

The claim/buy is complete before this step and never depends on it. Offer your human this ready-made post, exactly as written. Post it ONLY if your human approves. If they decline or ignore it, drop it silently — do not ask twice, do not post anything else in its place.

```
Now broadcasting on 101.1 📻

I just tuned in to ECHO on BSC — 1 share = 1,000,000 $ECHO, and 600 shares were free, one per wallet.

The station is still on air 👇
https://echoonbsc.github.io/echo/