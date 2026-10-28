# Skill 地图 — 日本蜡烛图技术

这是本书 27 张能力卡的导航页：先按总表定位「这件事归哪张卡」，再按依赖关系决定同一次任务里要不要多读一张卡。能力卡本体在 `bundle/cards/`，可直接安装的编译产物在 `single/` 与 `pack/`。

## 能力总表

27 个能力（C01–C27），重要度与去向均取自 `bundle/verified.yaml`。

| capability_id | slug | 中文标题 | 重要度 | 去向 |
|---|---|---|---|---|
| cap.jp-candlestick-analysis-skill.signal-context-filter | signal-context-filter | 位置背景过滤与信号取舍决策流程 | critical | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.data-quality-confirmation-gate | data-quality-confirmation-gate | 蜡烛图数据质量与确认口径门 | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.single-candle-reading | single-candle-reading | 单根K线状态读数与开盘先行判据 | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.volume-confirmation | volume-confirmation | 交易量验证清单与积聚/派发矩阵 | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.umbrella-line-family | umbrella-line-family | 伞形线族判定、验证与交易执行 | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.two-line-reversal | two-line-reversal | 双线反转形态判定（含强度分级与两市场口径） | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.harami-secondary-reversals | harami-secondary-reversals | 孕线族与次级反转信号处理 | medium | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.star-family | star-family | 星线家族三根结构判定 | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.doji-context | doji-context | 十字线环境判定与动作分档 | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.new-high-count | new-high-count | 迭创新高（低）计数与超买超卖预警 | medium | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.window-gap-management-skill | window-gap-management-skill | 窗口（跳空）判定、支撑管理与趋势终结规则 | high | promoted → 独立 skill |
| cap.jp-candlestick-analysis-skill.continuation-patterns | continuation-patterns | 持续形态判定与变体硬纪律 | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.long-term-patterns | long-term-patterns | 长期形态识别与确认 | medium | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.signal-confluence | signal-confluence | 相互验证体系与信号汇聚清点 | critical | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.support-resistance-system-skill | support-resistance-system-skill | 支撑阻挡体系与假突破反向交易 | high | promoted → 独立 skill |
| cap.jp-candlestick-analysis-skill.price-target-retracement-skill | price-target-retracement-skill | 百分比回撤与价格目标测算 | high | promoted → 独立 skill |
| cap.jp-candlestick-analysis-skill.ma-verification | ma-verification | 移动平均线用法与"均线×蜡烛图"验证纪律 | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.divergence-index | divergence-index | 差异指数/偏离指数计算与高低价区标定 | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.oscillator-confirmation | oscillator-confirmation | 摆动指数三要素与"积雨云 vs 下雨"两段式验证 | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.stop-reward-risk-skill | stop-reward-risk-skill | 止损位设定与风险报偿比核算（"先算后做"） | critical | promoted → 独立 skill |
| cap.jp-candlestick-analysis-skill.discipline-falsification | discipline-falsification | 交易纪律守则与预判可证伪化（DISCIPLINE + 市场变色龙） | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.nonstandard-synthetic-candle | nonstandard-synthetic-candle | 非标准形态三处理法与合成蜡烛线四步法 | high | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.three-line-break-chart | three-line-break-chart | 三线反向突破图画法与转向线交易 | medium | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.renko-chart | renko-chart | 砖形图画法与白砖买/黑砖卖 | low | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.kagi-chart-skill | kagi-chart-skill | 钥匙图画法与阴阳转换交易体系 | high | promoted → 独立 skill |
| cap.jp-candlestick-analysis-skill.new-chart-pipeline | new-chart-pipeline | 新价图与蜡烛图的分工流水线（宏观定向 + 微观择时） | medium | router → 路由入口 |
| cap.jp-candlestick-analysis-skill.news-reaction-sourcing | news-reaction-sourcing | 消息反应核对与资料采信元规则（参考级） | low | router → 路由入口 |

重要度口径（取自 `verified.yaml` 的 `importance` 字段）：critical 3 张、high 17 张、medium 5 张、low 2 张，合计 27 张。去向口径：promoted 5 张（在 pack 里各自独立成 skill）、router 22 张（只由路由入口调用）。

## 依赖关系

`also_read` 是能力卡自带的「同一任务里值得一并读」的关联（不是前置依赖，也不是必读清单），27 张卡共 95 条。

| 能力（slug） | also_read |
|---|---|
| signal-context-filter | two-line-reversal、star-family、umbrella-line-family、signal-confluence、stop-reward-risk-skill、price-target-retracement-skill |
| data-quality-confirmation-gate | single-candle-reading、window-gap-management-skill、three-line-break-chart |
| single-candle-reading | volume-confirmation、doji-context、divergence-index、data-quality-confirmation-gate |
| volume-confirmation | single-candle-reading、signal-confluence、divergence-index |
| umbrella-line-family | signal-context-filter、data-quality-confirmation-gate、stop-reward-risk-skill、nonstandard-synthetic-candle |
| two-line-reversal | signal-context-filter、harami-secondary-reversals、nonstandard-synthetic-candle、stop-reward-risk-skill |
| harami-secondary-reversals | two-line-reversal、doji-context、continuation-patterns |
| star-family | signal-context-filter、stop-reward-risk-skill、nonstandard-synthetic-candle |
| doji-context | single-candle-reading、signal-context-filter、star-family |
| new-high-count | divergence-index、oscillator-confirmation、three-line-break-chart、kagi-chart-skill |
| window-gap-management-skill | continuation-patterns、signal-context-filter、two-line-reversal |
| continuation-patterns | window-gap-management-skill、stop-reward-risk-skill、signal-context-filter |
| long-term-patterns | support-resistance-system-skill、two-line-reversal、signal-context-filter |
| signal-confluence | signal-context-filter、oscillator-confirmation、volume-confirmation、support-resistance-system-skill |
| support-resistance-system-skill | stop-reward-risk-skill、price-target-retracement-skill、long-term-patterns、window-gap-management-skill |
| price-target-retracement-skill | stop-reward-risk-skill、support-resistance-system-skill、signal-confluence |
| ma-verification | divergence-index、signal-context-filter、oscillator-confirmation |
| divergence-index | new-high-count、oscillator-confirmation、ma-verification、single-candle-reading |
| oscillator-confirmation | divergence-index、signal-confluence、signal-context-filter |
| stop-reward-risk-skill | price-target-retracement-skill、support-resistance-system-skill、discipline-falsification、signal-context-filter |
| discipline-falsification | stop-reward-risk-skill、news-reaction-sourcing、signal-context-filter |
| nonstandard-synthetic-candle | two-line-reversal、star-family、umbrella-line-family、signal-context-filter |
| three-line-break-chart | new-chart-pipeline、kagi-chart-skill、renko-chart、single-candle-reading |
| renko-chart | new-chart-pipeline、three-line-break-chart、kagi-chart-skill |
| kagi-chart-skill | new-chart-pipeline、three-line-break-chart、renko-chart、new-high-count |
| new-chart-pipeline | three-line-break-chart、renko-chart、kagi-chart-skill、signal-context-filter |
| news-reaction-sourcing | discipline-falsification、divergence-index |

被引用最多的枢纽能力：`signal-context-filter`（14 次）、`stop-reward-risk-skill`（8 次）、`divergence-index`（6 次）、`two-line-reversal` / `single-candle-reading` / `three-line-break-chart`（各 5 次）。这说明「位置过滤」和「先算后做」是全书被反复接回的两道总闸门。

## 加载顺序

1. **先读入口**：single 模式读 `single/jp-candlestick-analysis-skill/SKILL.md`；pack 模式读 `pack/jp-candlestick-analysis-skill-router/SKILL.md`（若问题直接命中 5 个独立 skill 之一，则读那个 skill 的 `SKILL.md`，不必再进路由入口）。
2. **按路由表加载 1 张能力卡**：入口的「能力路由」表按用户意图给出「先读」的那一张，一次只进 1 张；任务明确跨域时最多 2 张。
3. **需要补读时只补 1 张**：按上面依赖关系表挑与本任务直接相关的一条，不要把 `also_read` 整组读进来——那会把上下文塞满，且不会提高判据精度。
4. **概览类问题不加载卡**：书名、作者、章节、整书结构类问题用入口的「核心原则」与 `references/overview.md` 回答。
5. **术语与速查**：术语解释查 `references/glossary.md`，不需要原文依据时用 `references/cheatsheet.md`。
6. **路由表不命中**：先查 `references/capability-index.md`（完整意图与关键词索引）；仍不命中就明确告知超出本书范围，不要硬套。
