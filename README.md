<h1 align="center">日本蜡烛图技术 Skill</h1>

<p align="center">中文 | <a href="README.en.md">English</a></p>

一套可直接使用的 AI skill 工具包——把史蒂夫·尼森《日本蜡烛图技术》与《日本蜡烛图技术新解》中的 K 线判读方法，蒸馏成 27 张可单独触发、也可组合调用的能力卡。

它不是原书摘要，也不是读后感，而是把书中可复用的方法论拆成可触发、可执行、可测试的 skill 模块。

## 这套 skills 能解决什么问题

- 看到一根「标准形态」就想下单，却说不清它出现在当前位置到底值不值得交易
- 把「反转形态」当成「见顶 / 见底」——它其实只宣告原趋势终止，之后可能掉头、转横或原样继续
- 同一价位同时亮起蜡烛图、均线、RSI、成交量信号，不知道该信哪个，也分不清其中哪些是同源指标堆叠（信息量并不增加）
- 缺口要不要回补、假突破能不能反手、止损放哪、这笔交易到底划不划算
- 手里只有收盘价或基金净值（没有开盘价），想知道怎么用三线反向突破图、砖形图、钥匙图判断方向
- 复盘时只会说「当时按规则做就好了」，缺一份可证伪的预案和交易前的纪律清单

## 蒸馏了什么

27 张能力卡，按「先过闸门、再读图、最后算账」的顺序组织。下列 slug 与 `bundle/verified.yaml` 的 27 个能力一一对应（`-skill` 后缀是规范化 slug 的一部分）：

- **决策闸门**（3 张）：`signal-context-filter`（位置背景过滤与信号取舍）、`signal-confluence`（相互验证体系与信号汇聚）、`stop-reward-risk-skill`（止损位设定与风险报偿比核算）
- **读图地基**（3 张）：`data-quality-confirmation-gate`（数据质量与确认口径门）、`single-candle-reading`（单根 K 线状态读数与开盘先行）、`volume-confirmation`（成交量验证与积聚 / 派发矩阵）
- **反转形态**（6 张）：`umbrella-line-family`（锤子线、上吊线、流星线、倒锤子线）、`two-line-reversal`（吞没、乌云盖顶、刺透，含强度分级与两市场口径）、`star-family`（启明星、黄昏星、弃婴、三星）、`doji-context`（十字线环境判定与动作分档）、`harami-secondary-reversals`（孕线族与次级反转信号）、`long-term-patterns`（头肩顶、三重顶、圆弧底等长期形态）
- **持续形态与位置**（7 张）：`continuation-patterns`（白三兵、上升三法、停顿形态）、`window-gap-management-skill`（窗口 / 跳空判定与支撑管理）、`support-resistance-system-skill`（支撑阻挡体系与假突破反向交易）、`ma-verification`（均线用法与「均线 × 蜡烛图」验证纪律）、`divergence-index`（差异指数 / 乖离率与高低价区标定）、`oscillator-confirmation`（RSI / 随机指数 / MACD 的两段式验证）、`new-high-count`（迭创新高计数与超买超卖预警）
- **执行与纪律**（3 张）：`price-target-retracement-skill`（百分比回撤与价格目标测算）、`discipline-falsification`（DISCIPLINE 纪律清单与可证伪预案）、`nonstandard-synthetic-candle`（非标准形态三处理法与合成蜡烛线四步法）
- **新价图**（4 张）：`three-line-break-chart`（三线反向突破图）、`renko-chart`（砖形图）、`kagi-chart-skill`（钥匙图，场外基金净值的唯一可用图形方案）、`new-chart-pipeline`（新价图与蜡烛图的分工流水线）
- **元规则**（1 张）：`news-reaction-sourcing`（消息反应核对与双来源采信）

合计 3 + 3 + 6 + 7 + 3 + 4 + 1 = 27 张。每张卡的完整判据、原文依据、书中案例、触发场景、可执行步骤与边界盲点，都在 `bundle/cards/` 的对应文件里。

## 两种打包模式：single 与 pack

同一套 27 张能力卡，按两种粒度各编译了一次。两者内容完全相同，区别只在「agent 能看到几个入口」。

| | single（单一入口） | pack（compact pack，多入口） |
|---|---|---|
| 可发现入口 | **1 个**：`jp-candlestick-analysis-skill` | **6 个**：1 个来源路由入口 + 5 个已晋级独立 skill |
| 27 张能力卡放在哪 | 全部在入口的 `references/capabilities/` 里，由入口按路由表按需加载 1–2 张 | 5 张高频卡把整张能力卡（R / I / A1 / A2 / E / B 六段）编进各自的 `SKILL.md`；其余 22 张只在 router 的 `references/` 里 |
| 触发方式 | 只有入口的 description 参与匹配，进入后靠路由表分流 | 5 个高频能力可被 description 直接命中，少一跳 |
| 升级维护 | 替换 1 个目录 | 替换 6 个目录 |

pack 里被晋级为独立 skill 的 5 张卡：

- `stop-reward-risk-skill` — 止损位与风险报偿比
- `price-target-retracement-skill` — 百分比回撤与价格目标测算
- `window-gap-management-skill` — 窗口（跳空）判定与支撑管理
- `support-resistance-system-skill` — 支撑阻挡体系与假突破反向交易
- `kagi-chart-skill` — 钥匙图画法与阴阳转换交易

### 该装哪一种

按你的工作方式选，**只装一种**：

| 你的工作方式 | 推荐 | 原因 |
|---|---|---|
| 用 DSH / Codex / Claude Code 等有 skills 目录，希望列表干净 | single | 只占 1 个入口，能力一张不少 |
| 日常问题高度集中在「止损放哪 / 目标价多少 / 缺口回补 / 支撑阻挡 / 钥匙图」 | pack | 这 5 类正是被晋级的独立 skill，能直接命中 |
| 要分发给多个 agent 或团队，各自按需取用 | pack | 可以只装其中几个独立 skill，不必整包 |
| 只想装一次、不想维护多个目录 | single | 升级时只替换 1 个目录 |

> 两版由同一个 Bundle 编译，能力内容一致。**同时安装会重复触发**，请只装一种。

## 效果示例

### 示例 1：连跌后的长下影线，能不能抄底

**用户问题**

「这票连跌五天，今天收出长下影线，收盘几乎在最高，是锤子线吧？能抄底吗？」

**skill 如何判断**

- 先过 `data-quality-confirmation-gate`：确认行情软件给的是真实开盘价——若「开盘价」恒等于前一日收盘，高开低开这层信息已被抹掉，判读要判停换源
- 进 `umbrella-line-family`：形状三判据逐条过——实体居区间上端（颜色无所谓）、下影线达实体高度的倍数区间、无或极短上影线；跌势之后定名锤子线，锤子线不强制次日验证
- 接 `signal-context-filter`：看它落在支撑区还是下跌中继，是否逆主要趋势
- 最后 `stop-reward-risk-skill`：止损由形态客观给定（这根 K 线低点下方，以收市价穿越为准），目标由西方工具供给，再算比值

**最终回答示例**

> 先别急着叫它锤子线，两件事要先确认：开盘价是不是真实开盘价，这根线是不是出现在有支撑的位置。两条都成立，它才是锤子线，而且锤子线本身不需要等第二天验证（上吊线、倒锤子线才必须）。但锤子线只说明「下跌可能停」，不说明「马上涨」——所以动作不是满仓抄底。另外先声明下影线倍数：两本书口径不一致（正文说至少 2 倍、术语表说 2–3 倍、《新解》说 3 倍以上），你这一轮用哪个值得写下来，否则同类形态会忽认忽不认。然后按 `stop-reward-risk-skill` 算账：止损放这根 K 线低点下方，收市价跌破才认错；目标价必须由支撑阻挡或回撤位给出，不能凭感觉。书里的沃尔玛锤子线就是这个对照——收市价追买的风险约 5 美元，等次日回抽到低端再买，风险明显缩小；但作者也提醒市场常常并不回调，这个权衡要事前做。还有一点：书里从未给出「报偿比合格线」（没有 2:1、3:1 这类参考值），这个阈值得你自己定并写进预案。

### 示例 2：跳空缺口三天没回补，能不能追

**用户问题**

「今天跳空高开留了个缺口，三天没回补，能不能追？」

**skill 如何判断**

- `window-gap-management-skill`：先过 A 股的无信息跳空过滤（停牌复牌、除权除息、集合竞价、涨跌停一字板造成的跳空要剔除或标注），再判定是不是真窗口——相邻两根蜡烛线的**影线**互不重叠才算，实体错开而影线搭接的「假跳空」不算，缺口再小（几美分）也算
- 登记：整个窗口区间是支撑资产，向上窗口的关键支撑在窗口底，巨量开启的窗口更坚实
- `signal-context-filter`：这个缺口出现在长期横盘的上沿，还是连涨之后的末端
- `price-target-retracement-skill` + `stop-reward-risk-skill`：量上方空间、定止损、比较「现价追入」与「等回抽」两种入场的比值

**最终回答示例**

> 「三天没回补」只说明支撑还在，它本身不是买入理由。窗口在蜡烛图体系里不是一段价格真空，而是一个有生命周期的支撑资产：先确认影线之间真的不重叠，再把它登记成区间——向上窗口的关键支撑在窗口底。价格回撤进窗口就是买点区间，不必精确等到某个价；止损预先设在「收市价跌破窗口底」。真正的失效信号是**收市价封闭窗口**：盘中跌破不算，周线按周五收市，封闭即意味着窗口开启前的趋势终结，那时才停止做多逻辑。至于「数满三个缺口要不要反手」——「三」只是文化参考标杆，数满三个只做保护性动作，不激进逆势，也不要猜它什么时候回补。最后用 `price-target-retracement-skill` 量出目标、用 `stop-reward-risk-skill` 比较现价追入与等回抽到窗口上沿的比值：两者止损位相同，等回抽的比值明显更好。

## 这些 skill 是怎么生成出来的

这套 skill 使用 **[cangjie-skill](https://github.com/kangarooking/cangjie-skill)** 的 RIA-TV++ 流水线生成，整个流程分六个阶段：

1. **整书理解（Adler 分析）**——用 Mortimer Adler 的分析阅读法，对全书做结构、解释、批判、应用四步拆解
2. **并行提取**——同时派多个专项提取器（框架、原则、案例、反例、术语），从原文中提取候选方法论单元
3. **三重验证筛选**——每个候选必须通过三项检验：书内至少有 2 处独立佐证（跨域）、能回答书中未明说的新问题（预测力）、不是常识（独特性）
4. **RIA++ 构造**——按 R（原文引用）/ I（用自己的话重写）/ A1（书中案例）/ A2（未来触发场景）/ E（可执行步骤）/ B（边界与盲点）六个维度结构化
5. **Zettelkasten 链接**——找出能力卡之间的依赖、对比、组合关系，生成能力索引与路由表
6. **触发与输出测试**——为每张卡设计触发盲测题（含诱饵题：该触发时要触发，不该触发时要沉默）与输出评测场景，未通过的卡回炉重做，回炉后再做回归验证

两本书的关系也影响蒸馏：一本是主体（形态字典 + 多技术参照体系），《新解》不是重复，它修正了部分判据（如股票市场的「宽版」口径），并新增差异指数与三种新价图。整书理解的产出在 `BOOK_OVERVIEW.md`，三重验证结论在 `verified.md`，规范化定义在 `bundle/verified.yaml`。

## 测试与验证

本仓库连生成过程的测试材料一起发布：触发用例在各 skill 目录的 `test-prompts.json` 里，逐项评分记录在根目录的 `test-results.md`——包含失败与回炉修复的完整过程，不是只留通过记录。

- **触发盲测**：should_trigger 25 / 25、should_not_trigger 18 / 18；另有 18 条 edge 用例，其中 15 条直接通过、2 条由入口以正确行为承接、1 条修 skill 后复测
- **输出评测**：27 个单元 × normal / boundary 两个场景，共 54 个场景。首轮 52 / 54 PASS（断言 252 / 255，98.8%），2 个失败（砖形图、钥匙图）经回炉修卡后回归全过，最终 54 / 54
- **判停维度**：38 / 38 条 judge_stop 断言全部通过——该拒答时拒答、该追问时追问，不硬给结论
- **无卡对照**：5 组同题不带 skill 的基线对照，如实记录了卡在哪些维度只有「中等偏有限」的增量（其中钥匙图一组基线首段曾反超卡版，正是修卡的直接证据）

## 仓库结构

```text
jp-candlestick-analysis-skill/
├── README.md              ← 你正在看的
├── README.en.md           ← English version
├── LICENSE                ← MIT
├── BOOK_OVERVIEW.md       ← 阶段 0 产出：全书 Adler 分析
├── DIGEST.md              ← 阶段 5 产出：面向读者的整书精华长文
├── INDEX.md               ← 阶段 3 产出：skill 总览 + 依赖关系
├── verified.md            ← 通过三重验证的 27 个单元
├── TEST_SUMMARY.md        ← 阶段 4 产出：压力测试摘要
├── CANGJIE_ADAPTATION.md  ← 仓颉适配说明
├── GITHUB_REPO.md         ← 仓库元数据
├── test-results.md        ← 测试结果记录
├── candidates/            ← 阶段 1 产出：原始候选池
│   ├── frameworks.md      ← 框架与方法候选
│   ├── principles.md      ← 原则 / 规则 / 计算候选
│   ├── cases.md           ← 书中案例候选
│   ├── counter-examples.md← 反例与边界候选
│   └── glossary.md        ← 术语候选
├── rejected/              ← 阶段 1.5 产出：被淘汰的单元 + 原因
├── bundle/                ← 编译事实源
│   ├── verified.yaml      ← 能力元数据、判据与去向
│   ├── cards/             ← 能力卡源文件（六段结构）
│   └── book/              ← overview.md + glossary.md
├── single/                ← single 模式（1 个入口 + 全部能力卡）
│   └── jp-candlestick-analysis-skill/SKILL.md  ← 入口：触发 + 路由表 + 加载规则
└── pack/                  ← pack 模式（1 个路由入口 + 5 个晋级 skill）
    └── */SKILL.md         ← 6 个 skill，每个附带 test-prompts.json
```

## 如何使用

先把仓库克隆下来：

```bash
git clone https://github.com/raphael-y7/jp-candlestick-analysis-skill.git
```

### 装 single（推荐先试这个）

```bash
# macOS / Linux
cp -r jp-candlestick-analysis-skill/single/jp-candlestick-analysis-skill ~/.agents/skills/
```

```powershell
# Windows
Copy-Item -Recurse .\jp-candlestick-analysis-skill\single\jp-candlestick-analysis-skill "$env:USERPROFILE\.agents\skills\"
```

### 装 pack

只复制含 `SKILL.md` 的目录，不要把 `pack/` 下的两个 json 一起拷进 skills 目录：

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

> `~/.agents/skills` 是 DSH 的 skill 目录；用别的 agent 时换成它自己的 skills 目录即可（例如 Claude Code 是 `~/.claude/skills`）。

### 怎么确认装好了

装完问一句「这只票的止损位该放哪、风险报偿比怎么算」，看 agent 是否直接进入 `stop-reward-risk-skill` 的核算流程（止损价由形态客观给定、目标价由西方工具供给、算完比值再决定做不做），而不是给你一段泛泛的技术分析。装的是 single 时，它会先读入口再按路由表进能力卡；装的是 pack 时，对应能力会被直接命中。

## 来源

- 《日本蜡烛图技术》史蒂夫·尼森 著
- 《日本蜡烛图技术新解》史蒂夫·尼森 著

## 声明

本仓库只发布蒸馏后的 skill、索引与规则速查材料，不包含原书 PDF、EPUB、OCR 文件、截图或全书转写稿。能力卡中出现的原文引用仅用于标注方法论出处和保持可审计性。

书中所有数字判据（下影线倍数、连续新高计数、差异指数阈值、均线参数等）都是案例与经验归纳，原书未提供统计回测背书，使用时需按标的自行测试并声明所用口径。本仓库内容不构成投资建议。

## License

[MIT](./LICENSE)
