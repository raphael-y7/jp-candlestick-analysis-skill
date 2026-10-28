<h1 align="center">JP Candlestick Analysis Skill</h1>

<p align="center"><a href="README.md">中文</a> | English</p>

An AI skill pack for immediate use — it distills the candlestick reading methods from Steve Nison's *Japanese Candlestick Charting Techniques* and *The New Japanese Candlestick Charting Techniques* into 27 capability cards that can be triggered individually or combined.

It is not a book summary, nor a reading response — it breaks the reusable methodology in the books into skill modules that can be triggered, executed and tested.

## What these skills solve

- You see a "textbook pattern" and want to buy, but cannot say whether it is worth trading at this particular location
- You treat a "reversal pattern" as a top or bottom call — in fact it only declares that the prior trend has ended; price may reverse, turn sideways, or simply continue
- Candlestick, moving average, RSI and volume signals all fire at the same price level, and you cannot tell which one to trust, nor which of them are same-source indicator stacks that add no information
- Whether a gap will be filled, whether a false breakout can be traded in reverse, where the stop goes, and whether the trade is worth taking at all
- You only have closing prices or fund NAVs (no opening price) and want to judge direction with three-line break charts, Renko charts or Kagi charts
- Post-mortems always end with "I should have followed the rules" — you lack a falsifiable plan and a pre-trade discipline checklist

## What was distilled

27 capability cards, organized in the order "pass the gates first, read the chart second, do the math last". The slugs below map one-to-one onto the 27 capabilities in `bundle/verified.yaml` (the `-skill` suffix is part of the canonical slug):

- **Decision gates** (3): `signal-context-filter` (location and context filtering), `signal-confluence` (mutual confirmation and signal clustering), `stop-reward-risk-skill` (stop placement and risk-reward calculation)
- **Reading foundations** (3): `data-quality-confirmation-gate` (data quality and confirmation conventions), `single-candle-reading` (single-candle state reading and opening-price leads), `volume-confirmation` (volume verification and the accumulation/distribution matrix)
- **Reversal patterns** (6): `umbrella-line-family` (hammer, hanging man, shooting star, inverted hammer), `two-line-reversal` (engulfing, dark cloud cover, piercing, with strength tiers and two market conventions), `star-family` (morning star, evening star, abandoned baby, tri-star), `doji-context` (doji context and action tiers), `harami-secondary-reversals` (harami family and secondary reversal signals), `long-term-patterns` (head and shoulders, triple top, rounding bottom)
- **Continuation patterns and location** (7): `continuation-patterns` (three white soldiers, rising three methods, pause patterns), `window-gap-management-skill` (window/gap assessment and support management), `support-resistance-system-skill` (support and resistance with false-breakout reversals), `ma-verification` (moving averages and the "MA × candlestick" verification discipline), `divergence-index` (disparity index and high/low price zones), `oscillator-confirmation` (RSI, stochastic and MACD two-stage verification), `new-high-count` (consecutive new highs and overbought/oversold alerts)
- **Execution and discipline** (3): `price-target-retracement-skill` (percentage retracements and price targets), `discipline-falsification` (the DISCIPLINE checklist and falsifiable plans), `nonstandard-synthetic-candle` (non-standard pattern handling and synthetic candles)
- **New price charts** (4): `three-line-break-chart`, `renko-chart`, `kagi-chart-skill` (the only usable charting option for off-exchange fund NAVs), `new-chart-pipeline` (splitting direction-finding from entry timing)
- **Meta rules** (1): `news-reaction-sourcing` (checking market reaction to news and two-source verification)

That is 3 + 3 + 6 + 7 + 3 + 4 + 1 = 27 cards. Every card's full criteria, source quotations, in-book cases, trigger scenarios, executable steps and boundaries live in the matching file under `bundle/cards/`.

## Two packaging modes: single and pack

The same 27 capability cards are compiled twice, at two granularities. The content is identical; the only difference is how many entries an agent can discover.

| | single (one entry) | pack (compact pack, multiple entries) |
|---|---|---|
| Discoverable entries | **1**: `jp-candlestick-analysis-skill` | **6**: one source router + 5 promoted standalone skills |
| Where the 27 cards live | All inside the entry's `references/capabilities/`, loaded 1–2 at a time by the router table | The 5 high-frequency cards embed the whole card (sections R / I / A1 / A2 / E / B) in their own `SKILL.md`; the other 22 live only in the router's `references/` |
| Triggering | Only the entry description participates in matching; routing happens after entry | The 5 high-frequency capabilities are matched directly, one hop fewer |
| Upgrades | Replace 1 directory | Replace 6 directories |

The 5 cards promoted to standalone skills in the pack:

- `stop-reward-risk-skill` — stop placement and risk-reward
- `price-target-retracement-skill` — retracements and price targets
- `window-gap-management-skill` — window (gap) assessment and support management
- `support-resistance-system-skill` — support/resistance and false-breakout reversals
- `kagi-chart-skill` — Kagi charting and yin/yang conversion trading

### Which one to install

Pick by the way you work, and **install only one**:

| How you work | Recommended | Why |
|---|---|---|
| You use DSH / Codex / Claude Code with a skills directory and want a clean list | single | Takes 1 slot, loses no capabilities |
| Your daily questions concentrate on "where is my stop / what is the target / will the gap fill / support and resistance / Kagi charts" | pack | Those are exactly the promoted standalone skills, matched directly |
| You distribute to several agents or teammates who pick what they need | pack | They can install only the standalone skills they want |
| You want to install once and maintain one directory | single | Upgrades replace a single directory |

> Both builds come from the same bundle and carry identical capabilities. **Installing both will double-trigger**, so pick one.

## Examples

### Example 1: a long lower shadow after five down days — can I buy the bottom?

**User question**

"This stock has fallen for five days straight. Today it printed a long lower shadow and closed near the high. That's a hammer, right? Can I buy the bottom?"

**How the skill reasons**

- First `data-quality-confirmation-gate`: verify the data vendor provides a real opening price — if the "open" always equals the previous close, the gap information is already gone and the reading must stop and change source
- Then `umbrella-line-family`: check the three shape criteria one by one — body at the upper end of the range (colour irrelevant), lower shadow reaching the body-height multiple, no or very short upper shadow; after a decline it is named a hammer, and hammers do not require next-day confirmation
- Then `signal-context-filter`: is it sitting on support, or is it a continuation of the decline? Is it against the primary trend?
- Finally `stop-reward-risk-skill`: the stop is objectively given by the pattern (below the low of this candle, judged on closing prices), the target must be supplied by a Western tool, and only then is the ratio computed

**Sample answer**

> Do not call it a hammer yet. Two things need confirming first: whether the opening price is a real opening price, and whether this candle sits on actual support. If both hold, it is a hammer — and a hammer does not need next-day confirmation (only hanging men and inverted hammers do). But a hammer only says "the decline may stop", not "it will rise now", so the action is not to buy with full size. Also declare the shadow multiple first: the two books disagree (the main text says at least 2×, the glossary says 2–3×, *The New* says 3× or more). Write down which value you use this round, otherwise you will recognize the same shape inconsistently. Then do the math with `stop-reward-risk-skill`: the stop goes below the low of this candle and is only confirmed by a close beyond it; the target must come from support/resistance or a retracement level, never from a gut feeling. The Walmart hammer in the book is exactly this comparison — buying at the close risked about 5 dollars, while waiting for the next day's pullback to the low end shrank the risk noticeably; but the author also warns that the market often does not pull back, so weigh both options beforehand. One more thing: the book never gives a pass line for the ratio (no 2:1 or 3:1 reference), so you must set that threshold yourself and put it in the plan.

### Example 2: a gap that has not been filled for three days — should I chase?

**User question**

"The stock gapped up today and left a gap. Three days later it is still unfilled. Should I chase?"

**How the skill reasons**

- `window-gap-management-skill`: first run the A-share no-information-gap filter (gaps from trading halts, ex-rights/ex-dividend, call auction or limit-up/limit-down one-word bars must be removed or flagged), then decide whether it is a real window — the **shadows** of the two adjacent candles must not overlap; a body gap with overlapping shadows does not count, and a tiny gap of a few cents does
- Registration: the whole window range is a support asset; the key support of an upward window is its bottom edge, and a window opened on huge volume is firmer
- `signal-context-filter`: does this gap sit at the top of a long trading range, or at the end of an extended run?
- `price-target-retracement-skill` + `stop-reward-risk-skill`: measure upside room, set the stop, and compare "chase now" against "wait for a pullback"

**Sample answer**

> "Three days unfilled" only means support is still there — it is not a reason to buy. In the candlestick system a window is not a stretch of price vacuum but a support asset with a life cycle: first confirm the shadows really do not overlap, then register it as a range — the key support of an upward window is its bottom edge. A pullback into the window is the buy zone, and you do not need to wait for an exact price; the stop is pre-set as "a close below the bottom edge of the window". The real invalidation is a **close that seals the window**: an intraday break does not count, weekly charts use Friday's close, and sealing means the trend that opened the window has ended — that is when the long logic stops. As for "should I reverse after three gaps" — "three" is only a cultural reference marker; after three you take protective action, never an aggressive counter-trend trade, and you do not guess when the gap will be filled. Finally, measure the target with `price-target-retracement-skill` and compare chasing now against waiting for a pullback to the upper edge with `stop-reward-risk-skill`: both use the same stop, and the pullback entry gives a clearly better ratio.

## How these skills were generated

These skills were produced with the **[cangjie-skill](https://github.com/kangarooking/cangjie-skill)** RIA-TV++ pipeline, in six stages:

1. **Whole-book comprehension (Adler analysis)** — apply Mortimer Adler's analytical reading method to the book: structure, interpretation, criticism, application
2. **Parallel extraction** — several specialized extractors (frameworks, principles, cases, counter-examples, terminology) mine candidate methodology units from the source text
3. **Triple verification** — every candidate must pass three checks: at least two independent in-book supports (cross-domain), the ability to answer questions the book never explicitly addresses (predictive power), and not being common sense (distinctiveness)
4. **RIA++ construction** — structure each unit along R (quotation) / I (restatement in own words) / A1 (in-book case) / A2 (future trigger scenario) / E (executable steps) / B (boundaries and blind spots)
5. **Zettelkasten linking** — map dependencies, contrasts and combinations between cards, producing the capability index and routing table
6. **Trigger and output testing** — write trigger blind tests (including decoy questions: fire when they should, stay silent when they should not) and output evaluation scenarios for every card; failing cards go back for rework and are re-verified afterwards

The relationship between the two books also shapes the distillation: one is the main body (a pattern dictionary plus a multi-technique reference system), while *The New* is not a repeat — it revises some criteria (such as the "wide" definition for stock markets) and adds the disparity index plus three new price-chart types. The whole-book output is in `BOOK_OVERVIEW.md`, the triple-verification conclusions are in `verified.md`, and the canonical definitions are in `bundle/verified.yaml`.

## Testing and verification

This repository publishes the test material from the generation process alongside the skills: the trigger cases live in each skill directory's `test-prompts.json`, and the item-by-item scoring log is `test-results.md` at the repository root — including the failures and the rework, not just the passes.

- **Trigger blind tests**: should_trigger 25 / 25, should_not_trigger 18 / 18; plus 18 edge cases — 15 passed directly, 2 were handled correctly by the entry, 1 was fixed and re-tested
- **Output evaluation**: 27 units × normal / boundary = 54 scenarios. The first round scored 52 / 54 (252 / 255 assertions, 98.8%); the two failures (Renko chart, Kagi chart) were fixed in the cards and passed on regression, ending at 54 / 54
- **Stop discipline**: all 38 judge_stop assertions passed — refusing when it should refuse, asking when it should ask, never forcing a conclusion
- **No-skill control**: 5 same-question baselines run without the skill, honestly recording where the cards add only "moderate to limited" value (in the Kagi group the baseline even beat the card build on the first pass — direct evidence for the rework)

## Repository layout

```text
jp-candlestick-analysis-skill/
├── README.md              ← Chinese version
├── README.en.md           ← you are reading this
├── LICENSE                ← MIT
├── BOOK_OVERVIEW.md       ← stage 0 output: Adler whole-book analysis
├── DIGEST.md              ← stage 5 output: reader-facing distilled long-form essay
├── INDEX.md               ← stage 3 output: skill map + dependencies
├── verified.md            ← 27 units that passed triple verification
├── TEST_SUMMARY.md        ← stage 4 output: stress-test summary
├── CANGJIE_ADAPTATION.md  ← cangjie adaptation notes
├── GITHUB_REPO.md         ← repository metadata
├── test-results.md        ← test result records
├── candidates/            ← stage 1 output: raw candidate pool
│   ├── frameworks.md      ← framework and method candidates
│   ├── principles.md      ← principle / rule / calculation candidates
│   ├── cases.md           ← case candidates from the book
│   ├── counter-examples.md← counter-example and boundary candidates
│   └── glossary.md        ← terminology candidates
├── rejected/              ← stage 1.5 output: rejected units + reasons
├── bundle/                ← compilation source of truth
│   ├── verified.yaml      ← capability metadata, criteria and destinations
│   ├── cards/             ← capability card sources (six sections)
│   └── book/              ← overview.md + glossary.md
├── single/                ← single-mode build (one entry + all capability cards)
│   └── jp-candlestick-analysis-skill/SKILL.md  ← entry: triggers + routing table + loading rules
└── pack/                  ← pack-mode build (one router + 5 promoted skills)
    └── */SKILL.md         ← 6 skills, each shipping a test-prompts.json
```

## Usage

Clone the repository first:

```bash
git clone https://github.com/raphael-y7/jp-candlestick-analysis-skill.git
```

### Install single (recommended first try)

```bash
# macOS / Linux
cp -r jp-candlestick-analysis-skill/single/jp-candlestick-analysis-skill ~/.agents/skills/
```

```powershell
# Windows
Copy-Item -Recurse .\jp-candlestick-analysis-skill\single\jp-candlestick-analysis-skill "$env:USERPROFILE\.agents\skills\"
```

### Install pack

Copy only the directories that contain a `SKILL.md`; do not copy the two JSON files under `pack/` into your skills directory:

```bash
# macOS / Linux
cd jp-candlestick-analysis-skill/pack
cp -r jp-candlestick-analysis-skill-router \
      stop-reward-risk-skill \
      price-target-retracement-skill \
      window-gap-management-skill \
      support-resistance-system-skill \
      kagi-chart-skill ~/.agents/skills/
```

```powershell
# Windows
$pack = ".\jp-candlestick-analysis-skill\pack"
$dest = "$env:USERPROFILE\.agents\skills"
@('jp-candlestick-analysis-skill-router','stop-reward-risk-skill','price-target-retracement-skill','window-gap-management-skill','support-resistance-system-skill','kagi-chart-skill') |
  ForEach-Object { Copy-Item -Recurse -LiteralPath (Join-Path $pack $_) -Destination $dest }
```

> `~/.agents/skills` is the DSH skills directory; with another agent, use its own skills directory (for example `~/.claude/skills` for Claude Code).

### How to verify the install

Ask: "Where should the stop go for this stock, and how do I compute the risk-reward ratio?" If the agent enters the `stop-reward-risk-skill` calculation flow (stop objectively given by the pattern, target supplied by a Western tool, ratio computed before deciding) instead of giving generic technical commentary, the install works. With the single build it reads the entry first and then routes to a card; with the pack build the matching capability is hit directly.

## Sources

- *Japanese Candlestick Charting Techniques* by Steve Nison
- *The New Japanese Candlestick Charting Techniques* by Steve Nison

## Notice

This repository publishes distilled skills, indexes and rule quick references only. It contains no PDF, EPUB, OCR files, screenshots or full-book transcripts of the source books. Quotations that appear in the capability cards serve solely to attribute methodology and keep the material auditable.

All numeric criteria in the books (shadow multiples, consecutive new-high counts, disparity thresholds, moving-average parameters, etc.) are case- and experience-based rules without statistical backtesting; test them on your own instruments and declare the convention you use. Nothing in this repository is investment advice.

## License

[MIT](./LICENSE)
