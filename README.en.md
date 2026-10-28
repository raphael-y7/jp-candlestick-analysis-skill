<h1 align="center">Japanese Candlestick Charting Skill</h1>

<p align="center"><a href="README.md">中文</a> | English</p>

An AI skill pack for immediate use — it distills the candlestick reading methods from Steve Nison's *Japanese Candlestick Charting Techniques (2nd Edition)* and *The New Japanese Candlestick Charting Techniques* into 27 capability cards that can be triggered individually or combined.

It is not a book summary, nor a reading response — it breaks the reusable methodology in the books into skill modules that can be triggered, executed and tested.

## What these skills solve

- You see a "textbook pattern" and want to buy, but cannot say whether it is worth trading at this particular location
- You treat a "reversal pattern" as a top or bottom call — in fact it only declares that the prior trend has ended; price may reverse, turn sideways, or simply continue
- Candlestick, moving average, RSI and volume signals all fire at the same price level, and you cannot tell which one to trust, nor which of them are same-source indicator stacks that add no information
- Whether a gap will be filled, whether a false breakout can be traded in reverse, where the stop goes, and whether the trade is worth taking at all
- You only have closing prices or fund NAVs (no opening price) and want to judge direction with three-line break charts, Renko charts or Kagi charts
- Post-mortems always end with "I should have followed the rules" — you lack a falsifiable plan and a pre-trade discipline checklist

## What was distilled

27 capability cards, organized in the order "pass the gates first, read the chart second, do the math last":

- **Decision gates**: `signal-context-filter` (location and context filtering), `signal-confluence` (mutual confirmation and signal clustering), `stop-reward-risk` (stop placement and risk-reward calculation)
- **Reading foundations**: `data-quality-confirmation-gate` (data quality and confirmation conventions), `single-candle-reading` (single-candle state reading and opening-price leads), `volume-confirmation` (volume verification and the accumulation/distribution matrix)
- **Reversal patterns**: `umbrella-line-family` (hammer, hanging man, shooting star, inverted hammer), `two-line-reversal` (engulfing, dark cloud cover, piercing), `star-family` (morning star, evening star, abandoned baby, tri-star), `doji-context` (doji context and action tiers), `harami-secondary-reversals` (harami family and secondary reversal signals), `long-term-patterns` (head and shoulders, triple top, rounding bottom)
- **Continuation patterns and location**: `continuation-patterns` (three white soldiers, rising three methods, pause patterns), `window-gap-management` (window/gap assessment and support management), `support-resistance-system` (support and resistance with false-breakout reversals), `ma-verification` (moving averages and the "MA × candlestick" verification discipline), `divergence-index` (disparity index and high/low price zones), `oscillator-confirmation` (RSI, stochastic and MACD two-stage verification), `new-high-count` (consecutive new highs and overbought/oversold alerts)
- **Execution and discipline**: `price-target-retracement` (percentage retracements and price targets), `discipline-falsification` (the DISCIPLINE checklist and falsifiable plans), `nonstandard-synthetic-candle` (non-standard pattern handling and synthetic candles)
- **New price charts** (from *The New Japanese Candlestick Charting Techniques*): `three-line-break-chart`, `renko-chart`, `kagi-chart` (the only usable charting option for off-exchange fund NAVs), `new-chart-pipeline` (splitting direction-finding from entry timing)
- **Meta rules**: `news-reaction-sourcing` (checking market reaction to news and two-source verification)

## Two packaging modes: single and pack

The same 27 capability cards are compiled twice, at two granularities. The content is identical; the only difference is how many entries an agent can discover.

| | single (one entry) | pack (compact pack, multiple entries) |
|---|---|---|
| Discoverable entries | **1**: `jp-candlestick-analysis-skill` | **6**: one source router + 5 promoted standalone skills |
| Where the 27 cards live | All inside the entry's `references/capabilities/`, loaded 1–2 at a time by the router table | 5 high-frequency cards become standalone skills; the other 22 stay in the router's `references/` |
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

- First `data-quality-confirmation-gate`: verify the data vendor provides a real opening price (if the open is always identical to the previous close, the gap information is already gone and the reading must be downgraded)
- Then `umbrella-line-family`: a small body at the top of the range with a long lower shadow after a decline is a hammer; hammers do not require next-day confirmation
- Then `signal-context-filter`: is it sitting on support, or is it a continuation of the decline? Is it against the primary trend?
- Finally `stop-reward-risk`: put the stop below the low of the lower shadow and compute the risk-reward ratio

**Sample answer**

> Do not call it a hammer yet. Confirm two things first: whether the opening price is a real opening price, and whether this candle sits on actual support. If both hold, it is a hammer — and a hammer does not need next-day confirmation. But a hammer only says "the decline may stop", not "it will rise now", so the action is not to buy with full size. Declare the shadow multiple first: the two books disagree (the main text says at least 2×, the glossary says 2–3×, *The New* says 3× or more). Write down which value you use this round, otherwise you will recognize the same shape inconsistently. Then do the math with `stop-reward-risk`: stop below the low of the shadow, and measure the room to the nearest resistance above. Note the book never gives a pass line for the ratio (no 2:1 or 3:1 reference), so you must set that threshold yourself and put it in the plan. Under A-share T+1 you can take a probe position overnight and add only after the next close clears the body of this candle.

### Example 2: a gap that has not been filled for three days — should I chase?

**User question**

"The stock gapped up today and left a gap. Three days later it is still unfilled. Should I chase?"

**How the skill reasons**

- `window-gap-management`: classify the gap first (breakaway / runaway / exhaustion); the gap itself forms a support band
- `signal-context-filter`: does this gap sit at the top of a long trading range, or at the end of an extended run?
- `price-target-retracement`: measure upside room with box height or measured moves
- `stop-reward-risk`: stop below the lower edge of the gap, and compare "chase now" against "wait for a pullback"

**Sample answer**

> An unfilled gap only means "support is still there" — it is not a reason to buy. Classify it first: if the gap opened at the top of a long range on clearly expanded volume, it looks like a breakaway gap; if it is the third or fourth gap of an extended advance, it is more likely an exhaustion gap, and the correct action there is to reduce, not to chase. Assuming a breakaway gap, the support band is the gap's upper and lower edges, and the stop goes below the lower edge. Measure the target with box height or a measured move and compare it with the stop distance. Chasing now and waiting for a pullback to the upper edge of the gap use the same stop, but the pullback entry gives a clearly better ratio — so "three days unfilled" is not enough reason to give up waiting.

## How these skills were generated

These skills were produced with the **[cangjie-skill](https://github.com/kangarooking/cangjie-skill)** RIA-TV++ pipeline, in six stages:

1. **Whole-book comprehension (Adler analysis)** — apply Mortimer Adler's analytical reading method to the book: structure, interpretation, criticism, application
2. **Parallel extraction** — several specialized extractors (frameworks, principles, cases, counter-examples, terminology) mine candidate methodology units from the source text
3. **Triple verification** — every candidate must pass three checks: at least two independent in-book supports (cross-domain), the ability to answer questions the book never explicitly addresses (predictive power), and not being common sense (distinctiveness)
4. **RIA++ construction** — structure each unit along R (quotation) / I (restatement in own words) / A1 (in-book case) / A2 (future trigger scenario) / E (executable steps) / B (boundaries and blind spots)
5. **Zettelkasten linking** — map dependencies, contrasts and combinations between cards, producing the capability index and routing table
6. **Trigger and output testing** — write trigger blind tests (including decoy questions: fire when they should, stay silent when they should not) and output evaluation scenarios for every card; failing cards go back for rework and are re-verified afterwards

The relationship between the two books also shapes the distillation: the 2nd edition is the main body (a pattern dictionary plus a multi-technique reference system), while *The New* is not a repeat — it revises some criteria (such as the "wide" definition for stock markets) and adds the disparity index plus three new price-chart types.

## Testing and verification

This repository publishes the test material from the generation process alongside the skills: every card ships with a `test-prompts.json` (trigger and boundary cases), `evals/` holds the output-evaluation tasks, assertions and blind-test records, and `test-results.md` is the item-by-item scoring log — including the failures and the rework, not just the passes.

- **Trigger blind tests**: should_trigger 25 / 25, should_not_trigger 18 / 18; plus 18 edge cases — 15 passed directly, 2 were handled correctly by the entry, 1 was fixed and re-tested
- **Output evaluation**: 27 units × normal / boundary = 54 scenarios. The first round scored 52 / 54; the two failures (Renko chart, Kagi chart) were fixed in the cards and passed on regression, ending at 54 / 54
- **Stop discipline**: all 38 judge_stop assertions passed — refusing when it should refuse, asking when it should ask, never forcing a conclusion
- **No-skill control**: 5 same-question baselines run without the skill, honestly recording where the cards add only "moderate to limited" value

## Repository layout

```text
jp-candlestick-analysis-skill/
├── README.md                      ← Chinese version
├── README.en.md                   ← you are reading this
├── LICENSE                        ← MIT
├── BOOK_OVERVIEW.md               ← whole-book comprehension (Adler four-step, stage 0 output)
├── verified.md                    ← triple-verification conclusions for the 27 canonical units
├── single/                        ← single-entry build
│   └── jp-candlestick-analysis-skill/
│       ├── SKILL.md               ← entry: triggers + routing table + loading rules
│       ├── BUILD_MANIFEST.json    ← build manifest and file hashes
│       ├── test-prompts.json      ← entry-level trigger and boundary cases
│       └── references/
│           ├── overview.md        ← whole-book overview
│           ├── capability-index.md  ← full intent and keyword index
│           ├── cheatsheet.md      ← decision-rule quick reference
│           ├── glossary.md        ← glossary
│           └── capabilities/      ← 27 capability cards
├── pack/                          ← multi-entry build (compact pack)
│   ├── BUILD_MANIFEST.json
│   ├── capability-destinations.json
│   ├── jp-candlestick-analysis-skill-router/
│   │   ├── SKILL.md               ← source router entry
│   │   └── references/            ← 27 cards + indexes, called by the router
│   ├── stop-reward-risk-skill/
│   │   ├── SKILL.md
│   │   └── test-prompts.json
│   ├── price-target-retracement-skill/
│   │   ├── SKILL.md
│   │   └── test-prompts.json
│   ├── window-gap-management-skill/
│   │   ├── SKILL.md
│   │   └── test-prompts.json
│   ├── support-resistance-system-skill/
│   │   ├── SKILL.md
│   │   └── test-prompts.json
│   └── kagi-chart-skill/
│       ├── SKILL.md
│       └── test-prompts.json
└── evals/                          ← output evaluation and blind-test records
    ├── test-results.md             ← item-by-item scoring and rework log
    ├── output-tasks__C01-C14.json
    ├── output-tasks__C15-C27.json
    ├── output-assertions__C01-C14.json
    ├── output-assertions__C15-C27.json
    ├── blind__kagi-chart__candlestick-analysis.json
    ├── blind__stop-reward-risk__price-target-retracement.json
    ├── blind__window-gap-management__support-resistance-system.json
    ├── all_skills_list.json
    └── router_cards_list.json
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

Ask: "Where should the stop go for this stock, and how do I compute the risk-reward ratio?" If the agent enters the `stop-reward-risk` calculation flow instead of giving generic technical commentary, the install works. With the single build it reads the entry first and then routes to a card; with the pack build the matching capability is hit directly.

## Sources

- *Japanese Candlestick Charting Techniques* by Steve Nison
- *The New Japanese Candlestick Charting Techniques* by Steve Nison
- Distilled from both books together, producing 27 capability cards

## Notice

This repository publishes distilled skills, indexes and rule quick references only. It contains no PDF, EPUB, OCR files, screenshots or full-book transcripts of the source books. Quotations that appear in the capability cards serve solely to attribute methodology and keep the material auditable.

All numeric criteria in the books (shadow multiples, consecutive new-high counts, disparity thresholds, moving-average parameters, etc.) are case- and experience-based rules without statistical backtesting; test them on your own instruments and declare the convention you use. Nothing in this repository is investment advice.

## License

[MIT](https://opensource.org/licenses/MIT)
