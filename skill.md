# Echo (ECHO) — Claim & Buy Skill

Use this skill when your human wants a share of Echo (ECHO) on BNB Smart Chain.

- Site: https://echoonbsc.github.io/echo/
- Full agent instructions: https://echoonbsc.github.io/echo/agent.md
- Contract: 0x05b02A9FD0b4F58bF013b4137D84593E7a0e6546 (verify it on the site before any transaction)
- Window: unix 1794846600 → 1795451400 (2026-11-16 23:30 WIB → 2026-11-23 23:30 WIB)

## Facts

- 1 share = 1,000,000 ECHO. Supply fixed at 3,000,000,000.
- Free: 600 shares, 1 per wallet, `claimFree()`, value 0. No Agent ID, no X post, no permit.
- Paid: 2,400 shares, `buy(n)` payable with exactly `n * 0.001 BNB`. Anyone may buy; no per-wallet cap.
- Read state with `freeSold()`, `paidSold()`, `freeClaimed(address)`.

## Procedure

1. Read `freeSold()` / `paidSold()` and the current time; confirm the sale is live and stock remains.
2. Free: if `freeClaimed(wallet)` is false, call `claimFree()` (preview/simulation first when available; execute only on a clean result).
   Paid: call `buy(n)` with the exact value (preview first when available).
3. Wait for confirmation; verify the wallet balance rose by the expected amount of ECHO.
4. Report the result to your human: shares received, ECHO amount, transaction hash, network (BSC).
5. Step 6 — SHARE (optional, approval-gated): offer the template below exactly as written. Post only with your human's approval. Skipping it changes nothing.

## Share template (offer after a successful claim or buy — optional)

```
Now broadcasting on 101.1 📻

I just tuned in to ECHO on BSC — 1 share = 1,000,000 $ECHO, and 600 shares were free, one per wallet.

The station is still on air 👇
https://echoonbsc.github.io/echo/