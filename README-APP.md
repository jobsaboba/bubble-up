# Bubble Up Racing

The Double Bubble selections, run as a **full permutation** — as a PWA.

**The pattern:** every day the Double Bubble rule picks the races where the
Holy Grail's top runner scores at least twice its second. Bubble Up takes
that day's picks and runs **n selections = n singles + every double + every
treble + … + one n-fold** (2 picks → 2 singles + 1 double; 3 → 3 + 3 + 1;
4 → 4 + 6 + 4 + 1; 6 → 63 lines). Win-only at the published odds — a line
pays only when **every leg wins**.

**The stake:** set per day in the app's stake box (default 10p per line) —
every number on the app scales with it, flat staking is linear. The season
back-run below is at the 10p reference stake.

**The run so far (1 Jan → now, 10p a line):** 294 lines over 74 days ·
**£29.40 staked → £506.37 returned** · +1622% ROI · best day 9 Nov
(6 picks, all won — the six-fold alone paid £71.60 of the £468.35 day).

| fold | lines | won | ROI |
|---|---|---|---|
| Singles | 111 | 66 | +74% |
| Doubles | 76 | 32 | +297% |
| Trebles | 57 | 24 | +1213% |
| 4-folds | 35 | 15 | +4114% |
| 5-folds | 13 | 6 | +12430% |
| 6-folds | 2 | 1 | +35702% |

- Live app: https://jobsaboba.github.io/bubble-up/
- Data: `data/<date>.json` (picks + every settled line at unit stake) +
  `data/stats.json` + `data/index.json` + `data/latest.json`

## Publish

Everything derives from the Double Bubble's published files (no network):

    python3 ~/racing-scripts/bubble_up.py --publish

Runs at 06:45 every morning (after Double Bubble's 06:25) and on the
half-hour settle tick from `results-refresh.sh`.

## App

Two views: **The day** (day tabs, stake box, day staked/return/P/L, then
every line grouped by fold size with legs, combined ×odds, badges and
returns) and **The run** (season totals, by-fold table, monthly P/L, best
day). Blue-bubbles icon, installable. Service worker cache: `bubup-v1` —
bump it and the version whenever `index.html` changes.

## Local repo

    ~/projects/bubble-up           ← this repo (main → GitHub Pages)
    ~/racing-scripts/bubble_up.py  ← the engine

Commits use identity `jobsaboba <160133851+jobsaboba@users.noreply.github.com>`.
