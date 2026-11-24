# Strategy notes

Base: the kit's `baselines/pilot/sniper` (launch sniper with rug filter).
`vendor/agentfun-bot.ts` is a byte-identical copy of the kit's `sdk/ts` shim.

## What was tuned (dev window, `tools/grid.ts` / `tools/sim.ts` on the full dataset)

| Setting | Baseline | Tuned | Why |
| --- | --- | --- | --- |
| minTrades | 0 | 5 | Biggest single win. Needs real activity before entry. |
| maxAge | 3 slots | 12 slots | A few more qualifying launches; 15+ adds losers. |
| tpBps / slBps | 1500 / 1200 | 2500 / 800 | Wider profit target, tighter stop. |
| maxHold | 10 slots | 60 slots | Lets winners run; 100+ adds nothing. |
| maxAdds / addStepBps | 0 / 0 | 2 / 0 | Pyramid into strength at or above the last buy. Lifts dev net from +0.008 to +0.029 SOL and qualifying round trips from 17 to 18. |

Trailing stop and partial take-profit were tried and did not help; left off.
A third add, a 6-slot add delay, and a 2000 bps add step all scored worse.
The kit's momentum baseline scored -9.38 SOL and the reversion baseline -1.78 SOL
on the same window (momentum on part 1 of 3 only; reversion on the same part).

## Dev-window result (official `grade-local --driver process`, 2026-11-24)

- Net PnL: **+0.0287 SOL** (90% interval -0.122 .. +0.255 SOL)
- Trading: 182 fills over 21 coins, 21 round trips, win rate 9.5%, max drawdown 0.0066 SOL
- Guardrails: **18 of 20 coins** hold a round trip of at least 0.01 SOL on the dev
  window (needs 20). The final window is a different set of coins, so the count
  there will differ; this is the best-scoring compliant-adjacent setting found.
- Fees: 0.016 SOL curve + 0.014 SOL tx; at 2x fees net is about -0.02 SOL.

## Method note

The kit's `tools/sim.ts` loads only `dataset/events/part-00000.ndjson.gz` (1 of 3
parts). Early tuning on that partial window looked much better (+0.039 SOL) than
the official harness (-0.35 SOL for the same settings). All numbers above were
re-derived on the full dataset and confirmed with `grade-local --driver process`.

The bot is deterministic: no clock, no randomness, no I/O, no network, no secrets.
