# Pump.fun Replay Sprint — Paper Bot, Real Ranking

make.fun coding entry for [Pump.fun Replay Sprint — Paper Bot, Real Ranking](https://make.fun/bounty/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122).

[![make.fun · u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122](https://make.fun/badge/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122.svg)](https://make.fun/bounty/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122?utm_source=github&utm_medium=readme&utm_campaign=u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122)
[![rank](https://make.fun/badge/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122/vansouthrace/pump-fun-replay-paper-bot/rank.svg)](https://make.fun/bounty/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122)
[![reward](https://make.fun/badge/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122/vansouthrace/pump-fun-replay-paper-bot/reward.svg)](https://make.fun/bounty/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122?utm_source=github&utm_medium=readme&utm_campaign=u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122)

Referral: https://make.fun/r/05vf2eby

## Strategy

A launch sniper with a rug filter, tuned on the kit's dev window (see STRATEGY.md).
It buys only launches that already show organic activity (at least 5 trades, at most
3 distinct early buyers, sells under 50% of buys), takes profit at +25%, cuts
losses at -8%, exits if the creator sells, and pyramids twice into strength.
Dev-window grade-local: **+0.029 SOL net, 182 fills, 21 coins** (18 of 20 coins
meet the 0.01 SOL round-trip guardrail on dev; the final window is a new sample).
The kit's momentum baseline scored -9.38 SOL on the same window; the untuned
sniper scored -0.14 SOL.
