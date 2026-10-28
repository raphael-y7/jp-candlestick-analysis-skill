# verified — 27 个规范单元验证结论汇总（阶段 2 装配登记）

> 合并链：331 候选 →（阶段 1.5 三重验证）55 验证单元（F25+P30）→（阶段 1.6 晋级门+合并）27 规范单元（unit-C01–C27）。
> 审计依据：verify\verify_frameworks.md（unit-F01–F25）、verify\verify_principles.md（unit-P01–P30）、verify\verify_evidence.md（c01–c40 / x01–x35）；合并规则与晋级门逐单元评审见 verify\canonical_units.md。
> V1=引文逐字回原文核验；V2=新问题纸面演练（walkthrough）；V3=任务增益。单元级 V1/V2/V3 沿用阶段 1.5 结论；C27 为参考级单元（V2/V3 有限通过，如实标注）。

## 一、汇总表（unit-C01–C27）

| unit | slug | title | merged_from | V1/V2/V3 | decision | promotion 去向 |
|---|---|---|---|---|---|---|
| C01 | signal-context-filter | 位置背景过滤与信号取舍决策流程 | F01(f01)+P01(p01,p15)+P02(p02,p03,p10,p14) | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C02 | data-quality-confirmation-gate | 蜡烛图数据质量与确认口径门 | P04(p05,p06,p07)（无 F 对应，独立成单元） | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C03 | single-candle-reading | 单根K线状态读数与开盘先行判据 | F02(f02,f03)+P06(p16,p17,p19,p26,p123) | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C04 | volume-confirmation | 交易量验证清单与积聚/派发矩阵 | F03(f04,f28)+P23(p18,p80–p84) | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C05 | umbrella-line-family | 伞形线族判定、验证与交易执行 | F04(f05,f06,f07)+P09(p27–p31)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C06 | two-line-reversal | 双线反转形态判定（含强度分级与两市场口径） | F05(f08,f09)+P10(p33,p34,p35,p50)+P11(p36–p40)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C07 | harami-secondary-reversals | 孕线族与次级反转信号处理 | F06(f10,f11)+P12(p41,p42)+P13(p20,p43–p47)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C08 | star-family | 星线家族三根结构判定 | F07(f12)+P14(p51–p55)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C09 | doji-context | 十字线环境判定与动作分档 | F08(f13)+P07(p11,p21–p24,p68)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C10 | new-high-count | 迭创新高（低）计数与超买超卖预警 | F09(f14)+P08(p25)+g77 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C11 | window-gap-management-skill | 窗口（跳空）判定、支撑管理与趋势终结规则 | F10(f15,f16)+P15(p56–p62,p64)+g34+三窗口词条 | pass/pass/pass | verified | **promoted → 自身 Skill（#3）** |
| C12 | continuation-patterns | 持续形态判定与变体硬纪律 | F11(f17,f18,f19)+P16(p63,p65)+P17(p48,p49)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C13 | long-term-patterns | 长期形态识别与确认 | F12(f20)+P18(p66,p67)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C14 | signal-confluence | 相互验证体系与信号汇聚清点 | F13(f21,f30,f31)+P05(p08,p09)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C15 | support-resistance-system-skill | 支撑阻挡体系与假突破反向交易 | F14(f22,f23,f24)+P19(p32,p69,p70,p71,p124)+g51/g52+术语词条 | pass/pass/pass | verified | **promoted → 自身 Skill（#4）** |
| C16 | price-target-retracement-skill | 百分比回撤与价格目标测算 | F15(f25,f29)+P20(p72)+P24(p04,p85–p90)+术语词条 | pass/pass/pass | verified | **promoted → 自身 Skill（#2）** |
| C17 | ma-verification | 移动平均线用法与"均线×蜡烛图"验证纪律 | F16 均线半区(f26)+P21(p73,p74,p75)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C18 | divergence-index | 差异指数/偏离指数计算与高低价区标定 | F16 差异指数半区(f36,f37 警示区)+P26(p97,p98,p99 reference)+g78 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C19 | oscillator-confirmation | 摆动指数三要素与"积雨云 vs 下雨"两段式验证 | F17(f27)+P22(p12,p76–p79)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C20 | stop-reward-risk-skill | 止损位设定与风险报偿比核算（"先算后做"） | F18(f32)+P25 止损/比值半区(p91,p92,p93,p94 reference)+术语词条 | pass/pass/pass | verified | **promoted → 自身 Skill（#1）** |
| C21 | discipline-falsification | 交易纪律守则与预判可证伪化 | F19(f33,f34)+P25 纪律/变色龙半区(p95,p96)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C22 | nonstandard-synthetic-candle | 非标准形态三处理法与合成蜡烛线四步法 | F20(f35)+P03(p13,p117,p118)+g85 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C23 | three-line-break-chart | 三线反向突破图画法与转向线交易 | F21(f38,f39)+P27(p100–p104,p106 verified；p105 needs_review 不入池)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C24 | renko-chart | 砖形图画法与白砖买/黑砖卖 | F22(f40)+P28(p107,p108)+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C25 | kagi-chart-skill | 钥匙图画法与阴阳转换交易体系 | F23(f41,f42)+P29(p109–p116)+术语词条 | pass/pass/pass | verified | **promoted → 自身 Skill（#5）** |
| C26 | new-chart-pipeline | 新价图与蜡烛图的分工流水线（宏观定向+微观择时） | F24(f43)+P27/P29 中 f43 对应判据+术语词条 | pass/pass/pass | verified | router → jp-candlestick-analysis-skill |
| C27 | news-reaction-sourcing | 消息反应核对与资料采信元规则（参考级） | F25(f44,f45 reference)+P30(p119 verified；p120/p121/p122 reference) | pass/有限/有限 | reference（参考级单元） | router → jp-candlestick-analysis-skill（叙述区+C21 检查项） |

结构差异说明：unit-F16（均线+差异指数合并验证）按输出契约拆为 C17（procedure）与 C18（calculation），其余均为 F 单元=流程 canonical、P 单元判据并入的合并。

## 二、统计

- 候选池：**331 条**（frameworks 45 + principles 124 + cases 40 + counter-examples 35 + glossary 87）。
- 三重验证：进入 244 条（glossary 87 条为共享素材层未入验证）；decision 分布 **verified 160 / reference 83 / needs_review 1（p105）/ rejected 0**。
- 验证单元：**55**（F 池 45→25：24 verified + 1 reference；P 池 124→30：30 verified，单元级）。
- 规范单元：**27**（C01–C27；26 verified + 1 reference 级 C27），落在 methodology 目标区间 22–28。
- 晋级去向：5 promoted（stop-reward-risk-skill / price-target-retracement-skill / window-gap-management-skill / support-resistance-system-skill / kagi-chart-skill）+ 22 router → jp-candlestick-analysis-skill；可发现入口总数 6 ≤ 预算 8。
- 术语词典：87 条候选逐条 V1 核验通过，异名合并 1 处后 **86 词条** → book/glossary.md（verified 5 / reference 81）。
- 引文核验：75/75 素材抽查逐字命中（verify_evidence.md 核验记录），0 虚构引用。
