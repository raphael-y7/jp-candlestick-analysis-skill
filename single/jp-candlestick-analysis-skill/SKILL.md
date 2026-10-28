---
name: jp-candlestick-analysis-skill
description: |
  当需要解读A股个股或场外基金净值的K线/收盘价序列时使用：识别单根与组合蜡烛图形态并验证真伪，按趋势方向与位置过滤信号，用成交量、均线、摆动指数、窗口、支撑阻挡等异源工具相互验证，测算百分比回撤与价格目标，计算止损与风险报偿比，最终给出买入/减仓/观望/放弃的可检查结论；也可绘制三线反向突破图、砖形图、钥匙图判定趋势方向与平仓时机（场外基金净值唯一图形方案）。核心价值：把“见形态就下结论”升级为“语义校准 → 位置过滤 → 相互验证 → 先算后做”的四步决策流程，封堵未验证即行动、单形态决策、假突破追单、超买当指令、跳空必回补等高频错误。
metadata:
  cangjie.generated-by: cangjie-tools v2.5.0
  cangjie.variant: single
  cangjie.bundle-id: bundle.jp-candlestick-analysis-skill
  cangjie.capability-count: 27
  cangjie.entrypoint-count: 1
---
# 日本蜡烛图技术（第二版+新解）合并蒸馏 — 全书能力入口

## 触发与不触发

**适用**：与本书能力域相关的咨询与任务（见下方路由表的意图列）。
**不适用**：
- 期权类建议（备兑/保护性期权为美国市场工具，A股多数标的无对等物）。
- 期货/外汇专属技法与 T+0 盘中试仓-收盘确认打法（A股 T+1 下未经验证的变形不提供）。
- 基本面与消息面分析（消息只按“市场对该消息的反应”核对，不做消息真伪与业绩判断）。
- 任何统计显著性承诺：不提供命中率、超额收益或回测背书。

## 核心原则（常驻速览，概览类问题读到这里即可回答）

1. 反转形态 = “趋势变化”信号：只宣告原趋势终止，方向须等后续证据（可能反转/转横/继续）；禁止单形态决策。
2. 位置比形态重要：先问趋势方向一致性、支撑/阻挡、超买超卖环境，再解读形态；逆主要趋势的信号只用于减仓保护，不用于开新仓。
3. 收市价是确认之锚：形态完成、突破有效、窗口封闭、新价图反转一律以收市价为准；上吊线/倒锤子线等必须次日验证。
4. 相互验证才行动：同一价位出现一群异源信号（蜡烛图×西方工具×成交量）才值得行动；同源指标堆叠（RSI+KDJ+MACD）不增加信息量。
5. 每个信号自带止损与失效价：入场前先算风险报偿比，不划算就放弃；收市到达证伪价即改判离场。
6. 蜡烛图不提供价格目标：目标由支撑阻挡、回撤位、箱体/对等运动/旗形/三角形测算，且只用于平仓、不用于开新仓。
7. 所有数字判据是参考标杆：下影线倍数、8–10 个新高、差异指数 ±10%、均线参数等须按标的自测并声明；本方法为案例与经验归纳，无统计回测背书。

## 能力路由（先读本表，按意图加载 1 张能力卡）

| 用户意图 | 先读 | 补读/备注 |
|---|---|---|
| 判断某个K线形态出现在这个位置该不该按它操作；逆主要趋势的看涨/看跌信号应该怎么处理；为什么形态很标准却不值得交易（位置与报偿比倒挂）；复盘某个形态信号失效的原因 | references/capabilities/signal-context-filter.md | references/capabilities/two-line-reversal.md、references/capabilities/star-family.md、references/capabilities/umbrella-line-family.md、references/capabilities/signal-confluence.md、references/capabilities/stop-reward-risk-skill.md、references/capabilities/price-target-retracement-skill.md |
| 检查行情软件K线数据能不能用于形态判读；盘中破位/突破到底算不算数；两本书定义冲突时选哪一版；声明本轮分析的确认口径与判据版本 | references/capabilities/data-quality-confirmation-gate.md | references/capabilities/single-candle-reading.md、references/capabilities/window-gap-management-skill.md、references/capabilities/three-line-break-chart.md |
| 解读单根大阳线/大阴线/长影线的含义；高开低开预示什么（开盘先行法）；光脚阳线/光头阴线（捉腰带线）怎么看及其失效；把单根K线的支撑阻力带登记进价位表 | references/capabilities/single-candle-reading.md | references/capabilities/volume-confirmation.md、references/capabilities/doji-context.md、references/capabilities/divergence-index.md、references/capabilities/data-quality-confirmation-gate.md |
| 高位放量滞涨是不是出货（派发判读）；低位放量抗跌/不涨是不是吸筹（积聚判读）；创新高但缩量健康吗；核对某个形态的量能配合是否合格 | references/capabilities/volume-confirmation.md | references/capabilities/single-candle-reading.md、references/capabilities/signal-confluence.md、references/capabilities/divergence-index.md |
| 长下影线是锤子线吗、能抄底吗；高位吊颈线/上吊线要不要跑；流星线/倒锤子线怎么处理（含验证要求）；伞形线出现后的试仓/加码/止损计划 | references/capabilities/umbrella-line-family.md | references/capabilities/signal-context-filter.md、references/capabilities/data-quality-confirmation-gate.md、references/capabilities/stop-reward-risk-skill.md、references/capabilities/nonstandard-synthetic-candle.md |
| 吞没形态成立吗、强度如何分级；乌云盖顶/刺透形态的判据核对（含宽严两版口径）；双线形态出现后的止损与失效价在哪；未过中点的非标准双线形态怎么算 | references/capabilities/two-line-reversal.md | references/capabilities/signal-context-filter.md、references/capabilities/harami-secondary-reversals.md、references/capabilities/nonstandard-synthetic-candle.md、references/capabilities/stop-reward-risk-skill.md |
| 高位包孕/孕线要不要清仓；十字孕线是什么信号；平头/反击线/三只乌鸦等次级信号如何定性；弱信号怎么与其他信号叠加使用 | references/capabilities/harami-secondary-reversals.md | references/capabilities/two-line-reversal.md、references/capabilities/doji-context.md、references/capabilities/continuation-patterns.md |
| 启明星/黄昏星成立吗、强度如何；弃婴/崩盘十字星/三星形态怎么识别；三根形态完成但价格已走远怎么办；星线形态的支撑/阻挡登记在哪 | references/capabilities/star-family.md | references/capabilities/signal-context-filter.md、references/capabilities/stop-reward-risk-skill.md、references/capabilities/nonstandard-synthetic-candle.md |
| 高位十字星是不是要变盘/见顶；下跌中的十字星能不能抄底；近似十字线（开收接近但不相等）算不算；十字线出现后仓位动作分几档 | references/capabilities/doji-context.md | references/capabilities/single-candle-reading.md、references/capabilities/signal-context-filter.md、references/capabilities/star-family.md |
| 判断是否涨太多/跌太多；超买超卖计数预警；数连续新高新低；趋势股止盈时机参考 | references/capabilities/new-high-count.md | references/capabilities/divergence-index.md、references/capabilities/oscillator-confirmation.md、references/capabilities/three-line-break-chart.md、references/capabilities/kagi-chart-skill.md |
| 判断缺口支撑/会不会回补；跳空后怎么操作；连续缺口要不要反手；岛形反转支撑阻挡判定 | references/capabilities/window-gap-management-skill.md | references/capabilities/continuation-patterns.md、references/capabilities/signal-context-filter.md、references/capabilities/two-line-reversal.md |
| 判断白三兵/三连阳能不能追；判断上升三法等持续形态成立与否；持仓要不要加仓；识别停顿形态防误做空 | references/capabilities/continuation-patterns.md | references/capabilities/window-gap-management-skill.md、references/capabilities/stop-reward-risk-skill.md、references/capabilities/signal-context-filter.md |
| 判断头肩顶/三重顶等大级别顶底；颈线破位后怎么操作；圆弧底/锅底识别；长线清仓时机 | references/capabilities/long-term-patterns.md | references/capabilities/support-resistance-system-skill.md、references/capabilities/two-line-reversal.md、references/capabilities/signal-context-filter.md |
| 汇总多信号研判；验证多重确认是否有效；判断关键价位强度；识别同源指标堆叠幻觉 | references/capabilities/signal-confluence.md | references/capabilities/signal-context-filter.md、references/capabilities/oscillator-confirmation.md、references/capabilities/volume-confirmation.md、references/capabilities/support-resistance-system-skill.md |
| 判断假突破；支撑变阻力/极性转换登记；画趋势线与破位确认；假突破反向交易规则 | references/capabilities/support-resistance-system-skill.md | references/capabilities/stop-reward-risk-skill.md、references/capabilities/price-target-retracement-skill.md、references/capabilities/long-term-patterns.md、references/capabilities/window-gap-management-skill.md |
| 测算目标价；计算百分比回撤位；箱体/对等运动/旗形/三角形测算；止盈位设定 | references/capabilities/price-target-retracement-skill.md | references/capabilities/stop-reward-risk-skill.md、references/capabilities/support-resistance-system-skill.md、references/capabilities/signal-confluence.md |
| 判断均线支撑阻挡；站上/跌破均线怎么操作；金叉死叉含义；均线附近信号验证 | references/capabilities/ma-verification.md | references/capabilities/divergence-index.md、references/capabilities/signal-context-filter.md、references/capabilities/oscillator-confirmation.md |
| 计算乖离率/差异指数；量化超买超卖；判断高价区低价区；监测乖离背离 | references/capabilities/divergence-index.md | references/capabilities/new-high-count.md、references/capabilities/oscillator-confirmation.md、references/capabilities/ma-verification.md、references/capabilities/single-candle-reading.md |
| 判读 RSI/随机指数/MACD 的超买超卖、背离、交叉并决定是否行动；用随机指数买进三条件核对买入候选；管理"指标与蜡烛信号谁先谁后"的时序预期；识别并拒绝同源指标堆叠的伪确认 | references/capabilities/oscillator-confirmation.md | references/capabilities/divergence-index.md、references/capabilities/signal-confluence.md、references/capabilities/signal-context-filter.md |
| 为候选交易设定客观止损位（形态隐含止损位清单）；计算风险报偿比并裁决交易/放弃；比较现价追入与等回抽两种入场的比值差异；绑定入场即设止损、只上调不下调的纪律 | references/capabilities/stop-reward-risk-skill.md | references/capabilities/price-target-retracement-skill.md、references/capabilities/support-resistance-system-skill.md、references/capabilities/discipline-falsification.md、references/capabilities/signal-context-filter.md |
| 为方向预判设定可证伪的证伪价/证伪区；预写 if-then 交易预案；交易前过 DISCIPLINE 纪律自查清单；到证伪价强制改判与反向信号逐级改判 | references/capabilities/discipline-falsification.md | references/capabilities/stop-reward-risk-skill.md、references/capabilities/news-reaction-sourcing.md、references/capabilities/signal-context-filter.md |
| 裁决"这算不算某形态"的近似形态判读；用合成蜡烛线压缩多根 K 线并用单根法则定性；人工复核软件形态筛选排除的近似形态 | references/capabilities/nonstandard-synthetic-candle.md | references/capabilities/two-line-reversal.md、references/capabilities/star-family.md、references/capabilities/umbrella-line-family.md、references/capabilities/signal-context-filter.md |
| 按规则 1–11 画三线反向突破图；用连续白线/黑线与转向线判定趋势方向与反转；应用黑白鞋/白套装/脖颈口诀与确认档位交易 | references/capabilities/three-line-break-chart.md | references/capabilities/new-chart-pipeline.md、references/capabilities/kagi-chart-skill.md、references/capabilities/renko-chart.md、references/capabilities/single-candle-reading.md |
| 按砖值规则画砖形图；应用白砖买/黑砖卖的单一反转信号；识别横盘拉锯状态并调整砖值或停用 | references/capabilities/renko-chart.md | references/capabilities/new-chart-pipeline.md、references/capabilities/three-line-break-chart.md、references/capabilities/kagi-chart-skill.md |
| 按转向值规则画钥匙图（个股或基金净值）；用阴阳粗细转换产生买卖信号；读肩腰序列、中点规则、双窗口与多级突破；选择绝对值/百分比转向值（3%/5% 参考）并管理滞后预期 | references/capabilities/kagi-chart-skill.md | references/capabilities/new-chart-pipeline.md、references/capabilities/three-line-break-chart.md、references/capabilities/renko-chart.md、references/capabilities/new-high-count.md |
| 编排新价图与蜡烛图的组合使用流程；分离方向判定与入场时点的归属；管理新价图信号滞后的预期（抓主段不逃顶） | references/capabilities/new-chart-pipeline.md | references/capabilities/three-line-break-chart.md、references/capabilities/renko-chart.md、references/capabilities/kagi-chart-skill.md、references/capabilities/signal-context-filter.md |
| 核对市场对重大消息的反应（该涨不涨/该跌不跌）；登记并跟踪利空试探位；对单一来源说法与传闻做采信核对（双来源规则） | references/capabilities/news-reaction-sourcing.md | references/capabilities/discipline-falsification.md、references/capabilities/divergence-index.md |

**非能力类查询**：
- 书名/作者/章节/整书概览 → references/overview.md
- 术语解释 → references/glossary.md
- 决策规则速查（不需要原文依据时） → references/cheatsheet.md
- 完整意图与关键词索引（本表未覆盖的意图先查这里） → references/capability-index.md

## 加载规则

- 每次任务先读本文件，再按路由表加载 **1** 张能力卡；任务明确跨域时最多加载 2 张。
- 概览/书名类问题不加载能力卡，用「核心原则」与 overview.md 回答。
- 路由表与 capability-index.md 都无法命中的意图，明确告知超出本书范围，不要硬套。

## 边界与判停

- 数据门不过：开盘价被前收盘冒充（无真实开盘价）→ 停止形态判读，要求更换数据源（高开低开信号已丢失）。
- 无趋势可反转：横盘箱体中部的十字线/小实体群等 → 直接输出“信号无意义，不动作”并停止该信号的解读。
- 证伪触发：收市价越过预登记的证伪价/止损价 → 停止原判断，输出改判/离场结论，不寻找继续持有的理由。
- 风险报偿比不划算且无更优入场位 → 判停为“放弃交易”，不为该信号继续寻找买入理由。
- 用户索要期权策略或 T+0 技法 → 声明超出范围并停止。
