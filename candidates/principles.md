# 原则/规则/公式/口径候选 — 《日本蜡烛图技术（第二版）》+《日本蜡烛图技术新解》

> 提取器：principle-extractor（cangjie-skill 阶段 1）
> 倾向：辅助股票投资分析；期货/外汇专属规则已标注市场属性。
> 共 124 条候选（p01–p124，id 连续无缺口）。两书判据不一致处已并列记录，未擅自取舍。

## 一、总纲与位置背景原则（task-06 为主）

```yaml
- id: p01
  title: 反转形态实为"趋势变化形态"
  type: principle
  source_chapter: 上书 · 第四章 反转形态（引言）
  source_quote: |
    "当我说'反转形态'的时候，这个术语仅仅意味着之前的趋势将发生变化，但是未必一定会反转。
    把反转形态理解成趋势变化形态，才是慎重可取的考虑。"
  summary: |
    反转信号只宣告"原趋势终止"（汽车刹车灯比喻），之后市场可能反转、可能转横、也可能恢复原趋势。
    见到反转形态不得直接押注反向行情，须等待后续证据决定方向。
  tags: [principle, pattern, reversal, context]
  task_ids: [task-06, task-04]
  source_location: 上书《日本蜡烛图技术（第二版）》第四章 反转形态

- id: p02
  title: 趋势方向一致性原则：只有顺主要趋势的反转信号才能开新仓
  type: rule
  source_chapter: 上书 · 第四章 反转形态（引言）
  source_quote: |
    "只有当反转信号所指的方向与市场的主要趋势方向一致时，我们才能依据这个反转信号来开立新头寸。"
    逆着主要趋势的信号"构成了了结既有头寸的交易信号"。
  summary: |
    牛市中的顶部反转信号只用于平多/保护，不可据此做空；底部反转信号用于平空/观望。
    开新仓必须等顺主要趋势方向的信号（牛市找看涨信号买进，熊市找看跌信号卖出）。
  tags: [rule, trend, position-filter, stock-applicable]
  task_ids: [task-06]
  source_location: 上书第四章引言；下书第4章"趋势"节重复申明

- id: p03
  title: 形态的位置比形态本身更重要
  type: maxim
  source_chapter: 下书 · 第4章 蜡烛图与市场的整体技术面
  source_quote: |
    "一位日本交易员对此有一句很有道理的话：'形态的位置比形态本身更重要。'因此，当你决定测试
    某个蜡烛图形态的可靠性时，绝对不可以只根据这一个形态来进行买卖决策，首先必须分析形态所在的位置。"
  summary: |
    同一形态在阻挡位下方与支撑位发出的信号价值完全不同（图4-5沃尔玛：空头吞噬无交易价值，
    乌云盖顶反而是好机会）。判读任何信号前先看：趋势背景、支撑/阻挡、超买超卖、风险报偿比。
  tags: [maxim, position-filter, context]
  task_ids: [task-06]
  source_location: 下书第4章"蜡烛图形态出现的位置"；上书第四章引言同义表述

- id: p04
  title: 蜡烛图不提供价格目标，必须与西方工具结合
  type: principle
  source_chapter: 上书 · 第一章 引论（注意事项）
  source_quote: |
    "蜡烛图技术能够提供很多有价值的交易信号，但可惜的是，它并不提供价格目标。因此重要的一点是，
    一定要在蜡烛图上采用西方技术分析手段。"
  summary: |
    蜡烛图是分析工具而非完整交易系统：给出早期反转信号，不给行情幅度。
    目标必须来自支撑/阻挡、百分比回撤、趋势线、箱体突破、对等运动等西方工具（上书第16章专章）。
  tags: [principle, price-target, west-east-combo]
  task_ids: [task-18, task-06]
  source_location: 上书第一章；上书第十一章（"西方工具能够提供价格目标和止损区域"）

- id: p05
  title: 收市价是确认之锚（形态完成、突破、窗口封闭、新价图反转皆以收市价为准）
  type: rule
  source_chapter: 上书 · 第一章/第七章；下书 · 第3章/第2章
  source_quote: |
    "市场以收市价格向上超越某个阻挡水平或向下突破某个支撑水平……前者的意义更为重大。"
    "如果收盘价封闭窗口，则窗口出现之前的趋势就会结束。"
  summary: |
    日内穿越不算数：突破阻挡、跌破支撑、封闭窗口、确认形态，均须等收市价；
    周线图按周五收市价确认（窗口支撑被破的判定、缺口的止损均写明用周收盘）。
    代价：确认时价格可能已走远，故有盘中试仓+收盘加仓的变通（见 p105）。
  tags: [rule, confirmation, closing-price, core]
  task_ids: [task-01, task-07, task-15, task-22]
  source_location: 上书第一章"注意事项"、第七章窗口；下书第3章窗口节、第2章图2-13/2-14

- id: p06
  title: 形态判据取舍原则：以预测准确率高者为准
  type: principle
  source_chapter: 上书 · 第一章（注意事项）
  source_quote: |
    "碰到类似上述定义有分歧的时候，我的取舍原则是，哪一种说法能够为相应的价格形态的预测结果
    提供更高的准确率，哪一种就是恰当的。"
  summary: |
    蜡烛图定义存在多源分歧（如乌云盖顶要求开市价高于前日最高价还是仅高于收市价）。
    尼森的裁决法则是选预测准确率更高的一端；同时把日文"向上超越"统一解释为"收市价超越"。
  tags: [principle, criteria, ambiguity]
  task_ids: [task-04]
  source_location: 上书第一章"注意事项"

- id: p07
  title: 必须采用真实开盘价，不得用前收盘冒充
  type: rule
  source_chapter: 下书 · 第2章 蜡烛图的结构
  source_quote: |
    "某些数据供应商实际不提供每天真正的开盘价，而是将前一天的收盘价当做当天的开盘价。在我看来，
    这是不妥的……我们应该尽可能采用真正的开盘价，因为如果某日明显高开或低开……这将是一个不容忽视的市场信号。"
  summary: |
    数据口径规则：高开/低开本身是信号载体（开盘价与前一实体比较法、跳空形态都依赖真实开盘价）。
    用前收盘冒充开盘价会系统性丢失高开低开类信号。
  tags: [rule, data-quality, opening-price]
  task_ids: [task-01]
  source_location: 下书第2章"蜡烛图的结构"

- id: p08
  title: 相互验证原则：同一价位一群同向信号才值得行动
  type: principle
  source_chapter: 上书 · 第二部分引言 / 第十章
  source_quote: |
    "我们对相互验证的定义是'在同一个价位或接近同一个价位上，出现了一群相互验证的技术信号'……
    在某个支撑区域或阻挡区域，越多的信号汇集在一起，则出现反转的可能性越大。"
  summary: |
    单图版为"蜡烛线簇"：流星线、吞没、乌云盖顶等信号在同一水平反复出现，放大该区域重要性。
    纳斯达克2000年顶部即六重信号汇聚（上升阻挡线+流星线+60分钟看跌吞没+摆动指数顶背离+向下窗口+大风大浪线）。
  tags: [principle, confluence, confirmation, core]
  task_ids: [task-11, task-19]
  source_location: 上书第二部分引言、第十章；第十七章案例

- id: p09
  title: 异源验证优于同源堆叠（信息量概念）
  type: principle
  source_chapter: 上书 · 译者序
  source_quote: |
    "如果蜡烛图信号与西方技术分析信号不谋而合，则比起两种西方信号的相互验证更有说服力……
    一种常见的错误就是'近亲结婚'。有的朋友把几种本来同根同生的技术信号堆砌在一起，比如RSI、
    随机指数、MACD摆动指数等，作为一种相互印证的有力证据。"
  summary: |
    任何市场资料的信息量有极限，同源指标（摆动指数家族、均线与趋势线）信号高度重叠，堆叠几乎不增加信息量。
    蜡烛图×西方工具（趋势线/回撤/均线/量）是异源验证，才真正提高把握。
  tags: [principle, confluence, information-content]
  task_ids: [task-19]
  source_location: 上书译者序"不必厚此薄彼"（丁圣元）

- id: p10
  title: 非标准形态靠位置加持：关键位置的近似形态与标准形态同等有效
  type: rule
  source_chapter: 下书 · 第3章 启明星与主观性 / 第4章
  source_quote: |
    "如果某个非理想形态确认了一个支撑位或阻力位，或出现在严重超买或超卖区，形态构成反转信号的
    几率很大。举例来说，即使一根锤子线的下影线不是很长……但如果出现的位置正好是行情下跌到前一次
    涨幅的50%附近，那么我会认为，它包含了传统锤子线所蕴涵的所有多头信号价值。"
  summary: |
    三条加持条件：验证支撑/阻挡、处于严重超买卖区、伴随其他警告信号。
    A股实际图表标准形态罕见，这是把书用起来的关键桥梁；机械按标准筛选会漏掉关键信号。
  tags: [rule, nonstandard-pattern, position-filter]
  task_ids: [task-06, task-25]
  source_location: 下书第3章（M1/M2 案例）、第4章"如何决定一个蜡烛图形态的具体标准"

- id: p11
  title: 单一信号不定调：十字线不把趋势从上升改为下降
  type: rule
  source_chapter: 上书 · 第八章 神奇的十字线
  source_quote: |
    "如果出现了十字线，我不会把市场的短期趋势从上升调整为下降，但是会从上升调整为上升或中性。
    如果这根十字线同时与另一种技术信号相验证，就把趋势方向从上升调整为中性或下降。"
  summary: |
    信号强度分级响应：单信号→降级为中性并采取保护措施（减仓、上调止损、卖权）；
    双重验证→才允许方向性判断。适用于所有蜡烛图信号，防止"十字线！十字线！"式过度反应。
  tags: [rule, grading-response, cross]
  task_ids: [task-10, task-06]
  source_location: 上书第八章（北方十字线节）

- id: p12
  title: 蜡烛图信号经常领先西方工具约一周
  type: principle
  source_chapter: 上书 · 第十四章（MACD）
  source_quote: |
    "蜡烛图所发出的转折信号，经常领先于西方技术分析信号。在本图的情形下，我们看到乌云盖顶形态
    发出的顶部信号，比MACD发出的反转信号几乎提前了一周。"
  summary: |
    早信号的代价是伪信号多，因此才需要验证；西方交叉信号可作第二重确认（图14.8/14.10两例均先蜡烛后MACD）。
  tags: [principle, timing, lead-lag]
  task_ids: [task-16]
  source_location: 上书第十四章图14.8/14.10讲解

- id: p13
  title: 计算机筛选标准形态的危险：不能机械排除非标准形态
  type: principle
  source_chapter: 下书 · 第4章 计算机与蜡烛图
  source_quote: |
    "严格按标准工作的计算机，在筛选中就会排除这个形态。但是，如果这个非标准形态发生在重要阻力位呢？
    ……如果依赖计算机而忽略这个形态的空头信号，显然是危险的。"
  summary: |
    标准形态只是"信号标杆"；位置判断与主观裁量不可让渡给机器。
    自动化筛选可以找形态，但决策必须叠加趋势、位置、风险报偿比三道人工过滤。
  tags: [principle, computer-screening, subjectivity]
  task_ids: [task-06, task-25]
  source_location: 下书第4章"计算机与蜡烛图"全节

- id: p14
  title: 股市中"卖出信号"的落地方式（不可做空的替代动作）
  type: rule
  source_chapter: 下书 · 第1章 概述
  source_quote: |
    "本书使用'做空'、'卖出'等词汇讨论股票交易时，不必理解为卖出既有多头头寸，而是可以考虑在
    这种价位或这种时机卖出'限时到价买入权'，或者提高止损位，或冲销全部或部分头寸。"
  summary: |
    只能做多的市场（A股个人投资者）遇到看跌信号时的动作清单：清仓/减仓、上调止损、（有期权工具时）卖备兑。
    期权建议依赖美国个股期权市场，A股多数标的无对等工具——落地动作以减仓和止损为主。
  tags: [rule, stock-adaptation, exit-actions]
  task_ids: [task-06]
  source_location: 下书第1章末段说明

- id: p15
  title: 蜡烛图信号出现后市场未必立即按信号方向运动，可能只是强化支撑/阻挡区
  type: principle
  source_chapter: 上书 · 第七章（上升三法）
  source_quote: |
    "虽然蜡烛图信号经常发出市场转折的信号，但是它们并不意味着在信号出现后市场必定立即开始上涨……
    许多蜡烛图形态的出现，正如本图的这个实例，可能加强了某个支撑区域。"
  summary: |
    信号的一种正确用法是把形态低点/高点登记为支撑/阻挡水平（吞没、启明星、锤子线皆然），
    等市场回调到该区域再行动（"小口小口吃进"）。
  tags: [principle, s-r-conversion, patience]
  task_ids: [task-06, task-04]
  source_location: 上书第七章图7.27；第四章图4.19讲解

```

## 二、单根蜡烛线读数（task-02）

```yaml
- id: p16
  title: 长白/长黑实体判据（≥3倍前实体）及其实体中点支撑/阻力功能
  type: rule
  source_chapter: 下书 · 第2章 实体
  source_quote: |
    "一根具有明显意义的长白实体，其实体的长度至少应是前一天实体长度的3倍。"
    "行情一旦向下修正，会在这个长白实体的中点或蜡烛图底部（下影线的下端）获得支撑。"
  summary: |
    长实体阈值：实体长度≥前一（近期）实体的3倍（主观标杆）。
    长白实体=支撑区（中点至低点，下影线底端），回抽到中点附近可作早期买入信号，收盘跌破实体低点则重估多仓；
    长黑实体=阻力区（实体中点以上直至上影线顶点），也用于确认阻力/向下突破支撑的严重性。
  tags: [rule, long-body, calculation, threshold]
  task_ids: [task-02]
  source_location: 下书第2章"实体"全节及术语解释"长白蜡烛线/长黑蜡烛线"

- id: p17
  title: 开盘价与前一蜡烛线实体的比较（开盘定多空）
  type: rule
  source_chapter: 下书 · 第2章 开盘价与前一蜡烛线实体的比较
  source_quote: |
    "如果开盘价在前一根白线实体中点以下，行情呈空头态势。反之，如果开盘价在前一根黑线实体的
    中点以上，可视为一个积极信号……可以根据开盘价决定买卖，而不需等待收盘价。"
  summary: |
    激进交易者的盘中判据；无需等收市。期货开盘价远离前收盘的概率大、信号意义弱；
    股票开盘价通常贴近前收盘，一旦出现该形态意义更强——A股适用性高于美股期货。
  tags: [rule, opening-price, intraday]
  task_ids: [task-02]
  source_location: 下书第2章图2-28~2-30

- id: p18
  title: 纺锤线判据与筹码积聚/派发判读
  type: rule
  source_chapter: 下书 · 第2章 纺锤线 / 筹码积聚与派发
  source_quote: |
    "积聚发生在低价区：成交量放大而价格呆滞……派发与积聚正好相反。派发发生在高价区，表现为
    成交量放大而价格几乎停滞不动。……将纺锤线与成交量结合在一起考量，就可以判断是否有人在积聚或派发筹码。"
  summary: |
    纺锤线=小实体（颜色无关）+"市场喘息困难"；处于新高/急升后=动能衰减警讯。
    低价区放量呆滞（纺锤）=积聚→看涨；高价区放量停滞=派发→见顶。放量纺锤线创新低而无力守住，是底部征兆。
  tags: [rule, spinning-top, volume, accumulation-distribution-skill]
  task_ids: [task-02, task-17]
  source_location: 下书第2章；上书第三章纺锤线基础

- id: p19
  title: 影线位置规则：长上影/长下影/高浪线的环境判读
  type: rule
  source_chapter: 下书 · 第2章 上下影线 / 高浪线
  source_quote: |
    "一根长长的上影线，若发生在高价区、阻力区或超买区，就必须引起重视……有可能是走熊的一个征兆。
    反之，长长的下影线，如果出现在支撑区或超卖市道中……表示空头正在丧失控制权。"
  summary: |
    高浪线（上下影线都长、实体小）出现在趋势后="市场丧失方向感"，趋势岌岌可危。
    影线是信号载体而非噪声；单根长上影线线索微弱，需多根/后续信号确认。
  tags: [rule, shadow, high-wave]
  task_ids: [task-02]
  source_location: 下书第2章"上下影线""高浪线"；上书第八章"大风大浪线"

- id: p20
  title: 捉腰带线判据与失效条件
  type: rule
  source_chapter: 上书 · 第六章 捉腰带线
  source_quote: |
    "看涨捉腰带形态是一根坚挺的白色蜡烛线，其开市价位于本时段的最低点……如果市场收市于黑色的
    看跌捉腰带线之上，则意味着上升趋势已经恢复。如果市场收市于白色的看涨捉腰带线之下，则意味着
    市场的抛售压力重新积聚起来了。"
  summary: |
    看涨捉腰带=开盘光脚阳线（低价区看涨）；看跌捉腰带=开盘光头阴线（高价区看跌）。
    越长越重要；收市价反向穿越捉腰带线=信号失效。连续出现/配合阻挡区/久违地出现时分量更重。
  tags: [rule, belt-hold, invalidation]
  task_ids: [task-02]
  source_location: 上书第六章图6.19-6.22

- id: p21
  title: 十字星是过渡状态信号：等一两个时段明朗化，顶点为阻力
  type: rule
  source_chapter: 下书 · 第2章 十字星
  source_quote: |
    "交易者应该将其视为市场处于过渡状态的一个信号，而不是直接将它认定为反转蜡烛组合形态……
    十字星出现以后，交易者应该等待一两个交易时段，等待行情变化的明朗化。"
  summary: |
    十字星顶点（上影线顶端）构成阻力：见十字星卖出的投资者把买入止损设在顶点上方，收市上穿=市场"从疲劳中恢复"；
    下跌行情后见十字星买进者，卖出止损设在十字星低点下方（该十字星视为熊市持续信号）。
    十字星后的长白实体帮助确认其多头信号。
  tags: [rule, doji, transition, stop-placement]
  task_ids: [task-10]
  source_location: 下书第2章十字星节；上书第八章同义

- id: p22
  title: 十字线的位置规则：北方强、南方弱、箱体中无效
  type: rule
  source_chapter: 上书 · 第八章 神奇的十字线
  source_quote: |
    "当十字线出现时，在上升趋势中市场可能向下反转，而在下降趋势中市场则可能继续下跌……
    如果十字线出现在交易区间的环境下，便没有什么预测意义了，因为没有可反转的趋势。"
  summary: |
    北方十字线（上涨后）=顶部警讯，尤其长白酒线之后；南方十字线（下跌后）通常不作底部反转信号，
    除非验证支撑水平或伴随巨量；箱体中部的十字线无预测意义（仅区间顶/底处可验证支撑阻挡）。
  tags: [rule, doji, position-filter]
  task_ids: [task-10]
  source_location: 上书第八章图8.6、8.13-8.16

- id: p23
  title: 近似十字线四问法
  type: checklist
  source_chapter: 上书 · 第八章 神奇的十字线
  source_quote: |
    "1.看这根近似的十字线与其邻近的价格变化的相互关系……2.如果当时市场正处在一个重要的转折点。
    3.如果市场已经处在极度超买或超卖状态。4.如果当时已经有其他技术信号发出了警告信息。"
  summary: |
    开收市仅差几个最小报价单位时可否按十字线处理的自检清单；理论依据："宁可错认也不能漏过"。
    周围小实体密集→无意义；长实体之后、转折点、超买卖区、有其他信号→按十字线对待。
  tags: [checklist, doji, criteria]
  task_ids: [task-10]
  source_location: 上书第八章（近似十字线判定）

- id: p24
  title: 长白实体后的十字线：取两者最高高点为阻挡水平
  type: rule
  source_chapter: 上书 · 第八章 神奇的十字线
  source_quote: |
    "我在十字线和那根长长的白色蜡烛线中选择最高的高点（也就是最高的上影线顶点）。这个水平应当
    构成阻挡作用，以收市价作为判断是否突破的依据。"
  summary: |
    配套规则：若该十字线为当前行情创了收市价新高，须等看跌验证（次日收市价跌破十字线收市价）；
    收市价上穿该阻挡线=市场"休息好了"、看涨恢复的信号。
  tags: [rule, doji, resistance]
  task_ids: [task-10]
  source_location: 上书第八章图8.8/8.9/8.17

- id: p25
  title: 迭创新高（低）计数规则与中断重置
  type: rule
  source_chapter: 下书 · 第3章 迭创新高（低）
  source_quote: |
    "如果出现几乎连续的8~10个新高（或新低），则意味着先前的趋势面临改变的可能性大大增强。"
    "对于新高（低）蜡烛线的数目不必过于拘泥，8~10根只是个参考标杆而已……有些市场则可能是6根或者12根。"
  summary: |
    计数规则：新高蜡烛线=收盘创新高（从下行最低点后第二日高点抬高起算）；其间横向盘整蜡烛线可忽略，
    但不得超过两三根、不得出现强劲反向蜡烛线；一旦出现大幅修正或横向盘整化解超买卖，计数从新极点重新开始。
    动作：8~10个新高后停止买进/变现多仓（出现空头信号可卖空）；新低后反之。
  tags: [rule, counting, overbought-oversold, threshold]
  task_ids: [task-02]
  source_location: 下书第3章图3-76~3-80；新解第6/8章应用于三线图与钥匙图

- id: p26
  title: 实体的大小、频率与颜色判读横盘后的方向
  type: rule
  source_chapter: 下书 · 第2章 实体的大小、频率与颜色
  source_quote: |
    "方框内的蜡烛线中，有八根黑线，仅有四根白线。另外，黑线的长度大多超过白线。由于黑色实体
    比较多，而且比较长，显示空头更占优势。……这组横盘的蜡烛线组合所发出的信号，可以进一步证实
    西方理论的预测（窄幅整理之后，市场将重拾先前的走势）。"
  summary: |
    一组横盘蜡烛线的黑白数量与实体长度对比可读出多空倾向，与"箱体整理后顺原趋势"的西方理论互验。
  tags: [rule, body-frequency, consolidation]
  task_ids: [task-02]
  source_location: 下书第2章图2-25/2-26

```

## 三、伞形线族（task-03）

```yaml
- id: p27
  title: 伞形线（锤子线/上吊线）三条判据 — 两书数值并列
  type: rule
  source_chapter: 上书 · 第四章 伞形线；下书 · 术语解释 锤子线
  source_quote: |
    [第二版] "1.实体处于整个价格区间的上端，但实体本身的颜色无所谓。2.带有长长的下影线，且
    下影线的长度至少达到实体高度的两倍。3.在这类蜡烛线中，应当没有上影线；即使有上影线，长度也是极短的。"
    [新解术语表] "其长下影线通常为实体长度之3倍或以上。"
  summary: |
    判据核心一致（小实体居区间顶端+长下影+无/极短上影线），但下影线倍数两书不一致：
    第二版"至少2倍"、新解术语表"3倍或以上"，作者前后未统一——参数化时须声明区间并自行测试。
  tags: [rule, hammer, hanging-man, criteria-conflict]
  task_ids: [task-03]
  source_location: 上书第四章判据列表；下书术语解释"锤子线/吊颈线"（3倍版）

- id: p28
  title: 锤子线与上吊线的区分三要素（趋势/区间/验证）
  type: rule
  source_chapter: 上书 · 第四章 伞形线
  source_quote: |
    "锤子线只能紧接着在下跌行情后出现；上吊线必须紧接着在上涨行情后出现。……锤子线之前即便
    只有短线下跌也是有效的；但是，上吊线之前必须具备长足的上冲行情，最好是创下行情全历史新高后，
    方为有效。……上吊线出现后得到验证方为有效；对锤子线则无此要求。"
  summary: |
    同形异位：下跌后=锤子线（看涨），上涨后=上吊线（看跌）。上吊线要求更苛刻（长足上冲、最好历史新高），
    且必须验证；锤子线无验证要求（但下影线越长、实体越小、上影线越短越有效）。
  tags: [rule, hammer, hanging-man, position-filter]
  task_ids: [task-03]
  source_location: 上书第四章图4.4-4.12

- id: p29
  title: 上吊线必须等待验证；未验证则牛市依旧
  type: rule
  source_chapter: 上书 · 第四章 上吊线
  source_quote: |
    "最低限度的验证信号是，之后时段的开市价低于上吊线的实体。但是，我总是建议以收市价低于上吊线
    的实体为验证信号。……只要市场没有收市于上吊线实体的水平之下，则牛市趋势保持稳固。"
  summary: |
    机制：收在实体之下→上吊线当日开/收市买进的新多头全部被套→抛压。位于历史新高处的上吊线分量更重。
    图4.12反例：三根上吊线连续创新高且未获验证，市场继续上行——未验证的形态不构成卖出理由。
  tags: [rule, hanging-man, confirmation, counter-example-supported]
  task_ids: [task-03]
  source_location: 上书第四章图4.9-4.12

- id: p30
  title: 倒锤子线必须验证；流星线弱于吞没/黄昏星且不构成关键阻挡
  type: rule
  source_chapter: 上书 · 第五章 流星形态与倒锤子形态
  source_quote: |
    "验证信号既可以是次日开市价高于倒锤子线的实体，也可以是次日收市价高于倒锤子线的实体，尤其是
    后者更为有力。"……"我不认为流星线构成了关键阻挡水平。"
  summary: |
    倒锤子线（下降后长上影小实体）机制=次日上攻使倒锤子线当日做空者被套→空头回补螺旋。
    流星线（上涨后同形）通常只是次要顶部信号；墓碑十字线=流星线的无实体版，更疲软；流星线不设阻挡。
  tags: [rule, inverted-hammer, shooting-star, confirmation]
  task_ids: [task-03]
  source_location: 上书第五章图5.19-5.25

- id: p31
  title: 锤子线的两段建仓法与止损设定
  type: rule
  source_chapter: 下书 · 第3章 锤子线
  source_quote: |
    "我有时建议客户采用如下的交易方式：当锤子线刚出现时，先少量做多试水，如果价格拉回，并成功
    证实锤子线的支撑，再加码买进，完成多头头寸的建立。不管如何使用锤子线进行决策，止损点（以收盘价为准）
    可以设定在锤子线低点的下方。"
  summary: |
    锤子线后首波反弹常失败、行情回抽重测支撑（因为它必须出现在大跌之后）——盘中轻仓+回踩确认加仓；
    止损以收市价跌破锤子线低点为准。
  tags: [rule, hammer, position-building, stop-placement]
  task_ids: [task-03, task-20]
  source_location: 下书第3章图3-1~3-4

- id: p32
  title: 弹簧线（Spring）与上插线（Upthrust）：假突破反向判读
  type: rule
  source_chapter: 下书 · 第3章 锤子线（弹簧线节）
  source_quote: |
    "在价格突破支撑位后，空方无力将之压制在支撑位下方，于是出现了所谓的弹簧线。市场的这种情况
    证明，空头本来有机会控制盘面却最终失败，因此可以解读为转牛态势。"
  summary: |
    跌破支撑迅速收回=看涨（大鳄试盘的佯动解读）；上插阻力迅速跌回=看跌。
    完整交易规则（入场/止损/目标）见上书第十一章破低反涨/破高反跌（p60），两书为同一思想的两个表述。
  tags: [rule, spring, upthrust, false-breakout]
  task_ids: [task-12, task-03]
  source_location: 下书第3章图3-3/3-4、图3-14/3-15

```

## 四、双蜡烛线形态（task-04）

```yaml
- id: p33
  title: 吞没形态三条判别标准（含十字线例外）
  type: rule
  source_chapter: 上书 · 第四章 吞没形态
  source_quote: |
    "1.在吞没形态之前，市场必须处在明确的上升趋势（看跌吞没形态）或下降趋势（看涨吞没形态）中，
    哪怕这个趋势只是短期的。2.……第二根蜡烛线的实体必须覆盖第一根蜡烛线的实体（但是不一定需要
    吞没前者的上下影线）。3.……第二个实体应与第一个实体的颜色相反。（例外：第一条是十字线……）"
  summary: |
    趋势前提是硬条件（下降后的黑包白不是看跌吞没）；实体覆盖即可，影线不必覆盖；
    颜色相反例外：长跌后小白十字被大白酒线吞没仍可构成底部反转（顶反之）。
  tags: [rule, engulfing, criteria]
  task_ids: [task-04]
  source_location: 上书第四章图4.13-4.14

- id: p34
  title: 吞没形态强度分级三要素
  type: rule
  source_chapter: 上书 · 第四章 吞没形态；下书 · 第3章 吞噬形态
  source_quote: |
    "1.……第一天的实体非常小（即纺锤线），而第二天的实体非常大。2.如果吞没形态出现在超长延伸的
    或非常快速的市场运动之后。3.……第二个实体伴有超额的交易量。"
  summary: |
    下书补充：最严格定义=第二根长实体连影线完全包裹第一根（次严格=两者均含影线互相包裹）；
    两根实体长度大致相当→走势倾向横盘而非反转（可用于卖波动率）；空头吞噬发生在十字星之后，分量尤重。
  tags: [rule, engulfing, strength-grading]
  task_ids: [task-04, task-17]
  source_location: 上书第四章参考要素列表；下书第3章图3-33/3-34

- id: p35
  title: 吞没形态的高点/低点转化为阻挡/支撑水平
  type: rule
  source_chapter: 上书 · 第四章 吞没形态
  source_quote: |
    "在组成看跌吞没形态的两根蜡烛线中，选取其最高点。该高点构成了阻挡水平（以收市价来观察突破与否）。
    ……该形态的最低点构成了支撑水平。"
  summary: |
    用途一：形态完成时价已远离低点/高点，等回调到该支撑/反弹到该阻挡再入市（改善风险报偿比）。
    用途二：收市价上穿看跌吞没高点=看涨突破信号，可视为新一轮上涨的发端。
  tags: [rule, engulfing, s-r-conversion]
  task_ids: [task-04, task-20]
  source_location: 上书第四章图4.15-4.21

- id: p36
  title: 乌云盖顶判据（期货严定义+股票放宽版并列）
  type: rule
  source_chapter: 上书 · 第四章 乌云盖顶；下书 · 第3章 乌云盖顶
  source_quote: |
    [上书] "第二天的开市价超过了第一天的最高价……黑色实体的收市价向下穿入前一个白色实体的程度越深，
    则该形态构成市场顶部的机会越大。"
    [下书] "股票市场上的乌云盖顶形态在判定时更为灵活，第二根蜡烛线的开盘价只需要高于第一根蜡烛线的
    收盘价而不是最高价，即可判定。"
  summary: |
    标准判据：D2开市价高于D1最高价（尼森定义）+收市切入D1实体中点以下；未过中点=未完成形态，须等下一时段走弱确认。
    股票放宽：开市价高于前日收市价即可（A股语境的适用版本）；开市价高于前日最高价的版本信号更强。
  tags: [rule, dark-cloud, criteria, stock-flexibility]
  task_ids: [task-04]
  source_location: 上书第四章图4.22-4.25；下书第3章图3-17~3-22

- id: p37
  title: 乌云盖顶四项增强要素
  type: rule
  source_chapter: 上书 · 第四章 乌云盖顶
  source_quote: |
    "1.……黑色实体的收市价向下穿入前一个白色实体的程度越深……2.如果乌云盖顶形态发生在一个超长程的
    上升趋势中……3.……黑色实体的开市价高于某个主要的阻挡水平，但是市场未能成功地坚守住……4.如果在
    第二天开市的时候，交易量非常大，那么这里可能发生'胀爆'现象。"
  summary: |
    要素4（开市创新高+巨量=新多头集体被套）及"极高的持仓量"警告为期货语境；股票版取前四要素的量价部分。
    刺透形态的四项参考因素与此相同、方向相反。
  tags: [rule, dark-cloud, strength-grading, volume]
  task_ids: [task-04]
  source_location: 上书第四章增强要素列表

- id: p38
  title: 乌云盖顶/看跌吞没的失效条件与止损位
  type: rule
  source_chapter: 上书 · 第四章；下书 · 第3章/第4章
  source_quote: |
    "如果在乌云盖顶形态之后……出现了一根长长的白色实体，而且其收市价超过了这两种形态的最高价，
    那么这可能预示着新一轮上冲行情的到来。"……"如果见乌云盖顶形态就卖出，止损点应该设定在乌云盖顶
    形态的高点之上；如果考虑买进，应该等待收盘价穿越乌云盖顶形态的高点后进场。"
  summary: |
    形态高点同时是失效价位与止损参考：收市上穿=空头判断作废、转为看涨突破信号。
    每个信号自带失效条件——这是"信号可证伪"原则的具体化。
  tags: [rule, dark-cloud, invalidation, stop-placement]
  task_ids: [task-04, task-20]
  source_location: 上书第四章；下书第4章图4-1（收市上穿乌云盖顶=再度上行信号）

- id: p39
  title: 刺透形态必须过中点、无灵活余地；待入/切入/插入三形态皆弱
  type: rule
  source_chapter: 上书 · 第四章 刺透形态
  source_quote: |
    "在刺透形态中，白色蜡烛线的实体必须向上推进到黑色蜡烛线实体的中点以上。……在刺透形态中，
    却没有什么灵活的余地。……只要记住，白色实体必须推升到黑色实体的中点以上，才能构成较为有效的
    底部反转信号。"
  summary: |
    未达中点的三种形态（待入线/切入线/插入线）在下降趋势中皆为看跌持续信号（除非数日内接连两个插入线形态）。
    股票放宽：D2开市价低于D1收市价（不必低于D1最低价）仍可成立；插入线验证支撑区后可不等确认。
  tags: [rule, piercing, criteria]
  task_ids: [task-04]
  source_location: 上书第四章图4.26-4.32

- id: p40
  title: 看跌吞没（日全食）强于乌云盖顶（日偏食）——孤立比较下的强度排序
  type: principle
  source_chapter: 上书 · 第四章 乌云盖顶
  source_quote: |
    "我们不妨把乌云盖顶形态比作日偏食……而看跌吞没形态就像日全食……从这一点上说，作为顶部反转信号，
    看跌吞没形态比乌云盖顶形态具有更重要的技术意义。"
  summary: |
    排序依据：吞没的收市价低于前日整个实体、乌云盖顶仅切入实体内部。但该排序依赖语境——
    重要阻力位上的乌云盖顶可以强于普通位置的空头吞噬（图4-5沃尔玛判例）；孤立比形态无意义。
  tags: [principle, strength-ranking, context-dependent]
  task_ids: [task-04, task-06]
  source_location: 上书第四章；下书第4章图4-13（收盘位置图解）

- id: p41
  title: 孕线判据：实体包含（影线可超越）、第二实体越小越有力
  type: rule
  source_chapter: 上书 · 第六章 孕线形态
  source_quote: |
    "对孕线形态来说，所要求的全部条件是，第二个实体居于第一个实体内部，即使第二根蜡烛线的影线
    超越了第一根线的高点或低点也无所谓。"……"在孕线形态中，第二根实体越小，则整个形态越有力量。"
  summary: |
    与西方收缩日的区别：只要求实体被包含。十字孕线（第二根为十字）技术意义更强，称"呆滞形态"，顶部尤其有效。
    孕线亦可为中继：上升趋势中行情上破孕线高点=多头中继。
  tags: [rule, harami, criteria]
  task_ids: [task-04]
  source_location: 上书第六章图6.1-6.7

- id: p42
  title: 高价/低价包孕形态：预示横盘而非反转
  type: rule
  source_chapter: 下书 · 第3章 包孕形态
  source_quote: |
    "在一段上升后，如果第二个小实体靠近第一个长实体的上端，随后可能产生横向而非下跌的走势。我称
    这种组合为高价包孕形态……在下降趋势中，如果第二个小实体靠近第一个长实体的低点，此后很有可能产生
    横盘而非返身上涨的走势。我称这种组合为'低价包孕形态'。"
  summary: |
    标准包孕（第二实体位于前实体中点）→反转概率大；第二实体整体范围（含影线）都在前实体内→更可靠。
    高价/低价包孕的期权用法：预示波动率下降，可卖波动率。
  tags: [rule, harami, consolidation-forecast]
  task_ids: [task-04]
  source_location: 下书第3章图3-39~3-44

- id: p43
  title: 反击线判据：收市价相同（或足够接近），弱于刺透/乌云盖顶
  type: rule
  source_chapter: 上书 · 第六章 反击线形态
  source_quote: |
    "当两根颜色相反的蜡烛线具有相同的收市价时，就形成了一个反击线形态……刺透形态与看涨反击线形态
    相比较，是一种更为重要的底部反转信号。"
  summary: |
    判读弹性：次日收市价与前一收市价"足够接近"即可认定（图6.48）。看跌反击线开市价须高于前日最高价。
    反击线常用于验证既有阻挡/支撑区域。
  tags: [rule, counterattack, criteria]
  task_ids: [task-04]
  source_location: 上书第六章图6.45-6.50

- id: p44
  title: 分手线判据：开市价相同、颜色相反、两线平行
  type: rule
  source_chapter: 上书 · 第七章 分手线形态
  source_quote: |
    "看涨分手线形态的演变过程。在这类形态中，白色蜡烛线同时还应当是一根看涨捉腰带线（即其开市价
    位于或接近本时段最低点，收市价位于或接近本时段最高点）。"
  summary: |
    持续信号：上升趋势中阴线后开市跳空回到阴线开市价水平并收高=空头失去控制。难得一见。
    看涨分手线若出现在阻挡水平处（如28美元阻力），不应买入，须等收市上破阻力验证。
  tags: [rule, separating-lines, continuation]
  task_ids: [task-04]
  source_location: 上书第七章图7.31-7.34

- id: p45
  title: 平头形态：日线须兼具其他形态，周/月线可独立成立
  type: rule
  source_chapter: 上书 · 第六章 平头顶部形态和平头底部形态
  source_quote: |
    "对于日线图或日内图表上的平头形态，必须牢记的一个主要方面是，在同时具备其他特定蜡烛线组合特征
    的前提下，才可以根据平头形态采取行动。"……"在周蜡烛线图和月蜡烛线图中……这类形态甚至在没有其他
    蜡烛图信号相验证的条件下，也是成立的。"
  summary: |
    平头=数个时段试探同一高/低点（镊子）。日线理想组合=前长实体+后小实体同高/同低（常与孕线、十字、
    流星、上吊、锤子、刺透/乌云变体叠合）。时间尺度差异是判读关键。
  tags: [rule, tweezers, timeframe]
  task_ids: [task-04]
  source_location: 上书第六章图6.8-6.18

- id: p46
  title: 三只乌鸦判据：高价区/充分上涨后三根依次下降长黑
  type: rule
  source_chapter: 上书 · 第六章 三只乌鸦
  source_quote: |
    "如果连续出现了三根依次下降的黑色蜡烛线，则构成了所谓的三只乌鸦形态。如果三只乌鸦形态出现在
    高价格水平上，或者出现在经历了充分延伸的上涨行情中，就预示着价格即将下跌。"
  summary: |
    理想形态：每根开市价居于前一根实体之内、收市价接近最低点；开市价低于前一实体=更加疲软的变体。
    完成偏晚（第三根才确认），更适合长线交易者；第一根若是创新高后收低的反击线，可提前一个时段行动。
  tags: [rule, three-crows, criteria]
  task_ids: [task-04]
  source_location: 上书第六章图6.26-6.27

- id: p47
  title: 向上跳空两只乌鸦判据
  type: rule
  source_chapter: 上书 · 第六章 向上跳空两只乌鸦
  source_quote: |
    "在理想的向上跳空两只乌鸦形态中，第二个黑色实体的开市价高于第一个黑色实体的开市价，并且它的
    收市价低于第一个黑色实体的收市价。"
  summary: |
    罕见看跌形态：两次冲高均不能维持新高且次根收市更低。注意语境：若形态前有向上跳空（向上窗口坚挺信号），
    其看跌意义减弱（图6.25康宁判例）。
  tags: [rule, two-crows, criteria]
  task_ids: [task-04]
  source_location: 上书第六章图6.23-6.25

- id: p48
  title: 白三兵判据；前方受阻/停顿形态只可平多保护、不可开空
  type: rule
  source_chapter: 上书 · 第六章 白色三兵挺进形态
  source_quote: |
    "我们应当利用前方受阻形态和停顿形态来平仓了结已有的多头头寸，或者为多头头寸采取保护措施，
    但是不可据之开立空头头寸。"
  summary: |
    白三兵=三根依次上升白线、每根开市于前实体内/附近、收市于最高点或附近——稳健攀升。
    变体：前方受阻（实体递减/上影线变长）、停顿（长白+创新高后小实体）——牛方力量衰竭警讯，高位出现更须小心。
  tags: [rule, three-white-soldiers, advance-block, stall]
  task_ids: [task-08]
  source_location: 上书第六章图6.28-6.34

- id: p49
  title: 白三兵第1/2根白线内部构成回调支撑
  type: rule
  source_chapter: 上书 · 第六章 白色三兵挺进形态
  source_quote: |
    "在白三兵形态出现后，一旦行情调整，则其中的第一根或第二根白色蜡烛线，即白三兵的起点处，
    经常构成支撑水平。"
  summary: |
    白三兵完成后市场常回调（完成时价已离开低位，风险报偿比可能不佳），回调至第一根尤其第二根白线内部
    是预设买点；低吸止损设在白三兵起点低点下方。
  tags: [rule, three-white-soldiers, buy-zone]
  task_ids: [task-08, task-20]
  source_location: 上书第六章图6.32/6.33

- id: p50
  title: 最后吞噬形态：位置决定吞噬形态的多空属性
  type: rule
  source_chapter: 下书 · 第3章 最后吞噬形态
  source_quote: |
    "空头吞噬如果发生在下降走势中，则有可能是底部反转信号，这种形态称为最后吞噬底。如果此后的
    行情中收盘价位于形态中黑色实体的上方，则这一形态可以视为由空转多的信号。"
  summary: |
    最后吞噬顶=上升中的多头吞噬（须次日收市低于白线收盘确认转空；"双双殉情"喻）。同形不同位、含义反转——
    再次印证"位置高于形状"。
  tags: [rule, engulphing-variants, position-filter]
  task_ids: [task-04]
  source_location: 下书第3章图3-35~3-38（图3-38：巨量最后吞噬底+卖压高潮）

```

## 五、星线三根形态（task-05）

```yaml
- id: p51
  title: 启明星/黄昏星判据：决定性因素是第三根深入程度，跳空可有可无
  type: rule
  source_chapter: 上书 · 第五章 启明星/黄昏星
  source_quote: |
    "即使没有这个价格跳空，似乎也不会削减启明星形态的技术效力。其决定性因素是，第二根蜡烛线应为
    纺锤线，同时第三根蜡烛线应显著深入到第一根黑色蜡烛线内部。"
  summary: |
    三根结构：长实体+小实体星线+反向长实体。第二三根之间跳空非必要条件；第二三根实体重叠（构成吞没）
    亦无损效力（图5.4/5.9判例）。第三根深入越深、形态越强；第三根为小实体的黄昏星变体，配合位置仍有效。
  tags: [rule, morning-star, evening-star, criteria]
  task_ids: [task-05]
  source_location: 上书第五章图5.3-5.10；下书第3章图3-63~3-67

- id: p52
  title: 黄昏星增强要素（含理想量分布：第一根量小、第三根量大）
  type: rule
  source_chapter: 上书 · 第五章 黄昏星形态
  source_quote: |
    "1.如果第一根与第二根蜡烛线，第二根与第三根蜡烛线的实体之间不存在重叠。2.如果第三根蜡烛线的
    收市价向下深深扎入第一根蜡烛线的实体内部。3.如果第一根蜡烛线的交易量较小，而第三根蜡烛线的交易量较大。"
  summary: |
    黄昏星完成时价已远离顶点→风险报偿比评估：可按形态高点为止损、目标数倍于风险才值得做；否则等反弹至
    阻挡区再卖。形态高点构成阻挡水平。
  tags: [rule, evening-star, strength-grading, volume]
  task_ids: [task-05]
  source_location: 上书第五章参考要素列表、图5.10

- id: p53
  title: 十字启明/黄昏星与弃婴形态（影线互不接触的跳空十字）
  type: rule
  source_chapter: 上书 · 第五章 十字启明星和十字黄昏星
  source_quote: |
    "在十字黄昏星形态中，如果十字线的下影线既不与第一根蜡烛线的上影线重叠，也不与第三根蜡烛线的
    上影线重叠（即影线之间不相接触），这条十字线就构成了一个主要顶部反转信号，称为弃婴顶部形态。这种形态非常罕见！"
  summary: |
    十字启明/黄昏星=星线为十字的强变体；弃婴=前后均跳空且影线互不接触的十字岛（西方岛形反转的十字特例），
    极罕见；十字启明星低点、十字黄昏星高点构成支撑/阻挡。
  tags: [rule, doji-star, abandoned-baby]
  task_ids: [task-05]
  source_location: 上书第五章图5.11-5.18

- id: p54
  title: 崩盘十字星：十字跳空在长白实体之下的顶部反转
  type: rule
  source_chapter: 下书 · 第3章 黄昏星（崩盘十字星）
  source_quote: |
    "在高价区行情继续上行，此后出现一个向下跳空的十字星，卖压压倒了买盘。此后的一个交易时段如果是
    向下跳空的黑线，就构成了崩盘十字星。……这个形态被认为是'大跌的前兆'。"
  summary: |
    与黄昏十字星的唯一差异：十字的位置在第一根白线之下（黄昏星在白线之上）。
    与跳空十字（空头中继，出现于下降中）区分：崩盘十字星是顶部反转形态，出现于上升之后。
  tags: [rule, delisting-doji, criteria]
  task_ids: [task-05]
  source_location: 下书第3章图3-68/3-69

- id: p55
  title: 三川启明/黄昏星双关：形态极点=关键屏障（支撑/阻挡）
  type: rule
  source_chapter: 上书 · 第五章（历史小知识）
  source_quote: |
    "一旦这两类形态形成，就构成一道难以克服的屏障。也就是说，看涨的三川启明星形态应该成为重要的
    支撑水平，而看跌的三川黄昏星形态则构成了关键的阻挡水平。……当市场收市于黄昏星形态的阻挡水平之上
    （或启明星形态的支撑水平之下），便证明需求（或供给）方的军队已经夺取了战场的主动权。"
  summary: |
    形态极点=支撑/阻挡（黄昏星三根蜡烛线的最高点为止损/阻挡参考；收市穿越=形态失效确认）。
    名称典故：突破"三川"险阻后胜利唾手可得——突破后行情加速。
  tags: [rule, star-family, s-r-conversion]
  task_ids: [task-05]
  source_location: 上书第五章"历史小知识"；下书第3章图3-65

```

## 六、窗口与持续形态（task-07 / task-08）

```yaml
- id: p56
  title: 窗口判定规则：影线互不重叠才成立，窗口大小无关
  type: rule
  source_chapter: 上书 · 第七章 窗口
  source_quote: |
    "组成窗口的蜡烛线必须是影线之间互不重叠。无论两根蜡烛线实体之间的'缺口'有多大，除非在它们的
    影线之间存在缺口，否则不构成窗口。"……"无论向上的窗口多么小，它都应当构成潜在的支撑区域。"
  summary: |
    最常见误解辨正：实体不接触≠窗口。几美分的小窗口同样是支撑/阻挡；大窗口整个空间皆支撑/阻挡
    （紧凑性差）；向下窗口同理。
  tags: [rule, window, criteria]
  task_ids: [task-07]
  source_location: 上书第七章图7.1-7.3

- id: p57
  title: 窗口支撑/阻挡用法：整个窗口空间，关键支撑在窗口底部；收市封闭=趋势终结
  type: rule
  source_chapter: 上书 · 第七章 窗口；下书 · 第3章 窗口
  source_quote: |
    "向上的窗口的关键支撑水平位于窗口的底部（相应地，向下的窗口的关键阻挡水平位于窗口的顶部）。"
    "如果市场在向下回撤时收市价达到了窗口下边缘之下的水平，那么，先前的上升趋势就不复成立了。"
  summary: |
    顺窗口方向建仓：向上窗口回撤买入、向下窗口反弹卖出。日内跌破窗口底不算破，收市价为准（周线用周五收盘）；
    大窗口可早至窗口上缘附近进场，取决于交易风格与迫切程度。
  tags: [rule, window, s-r, closing-price]
  task_ids: [task-07]
  source_location: 上书第七章图7.1/7.4；下书第3章图3-45~3-48

- id: p58
  title: 窗口层级替代：一个窗口支撑被破，取其下方下一个窗口
  type: rule
  source_chapter: 上书 · 第七章 窗口
  source_quote: |
    "如果某个窗口的支撑被突破，那就在被突破的窗口下方寻找另一个窗口，以后者作为下一个支撑区域。"
  summary: |
    多窗口行情中逐级后撤的支撑管理（图7.4：窗口2破→看窗口1→再看大窗口底边）；
    向下窗口阻挡同理自下而上替代。
  tags: [rule, window, s-r-management]
  task_ids: [task-07]
  source_location: 上书第七章图7.4

- id: p59
  title: 尼森修正版三窗口理论：趋势持续到最后一个窗口被收市价关闭
  type: principle
  source_chapter: 上书 · 第七章 窗口；下书 · 第3章 三窗口理论
  source_quote: |
    "无论已经出现了多少个窗口，当前的趋势都不受影响，直到最后的窗口被关闭为止。在上升行情中，可以
    有任意数目的向上的窗口，只要市场没有以收市价向下突破最高的那个向上的窗口，则趋势依然维持向上。"
  summary: |
    对传统"三窗口=过度延伸"的修正（债券期货行情六窗口后创新高、封第六窗口才见大顶）。
    操作版：三窗口后可对冲/保护，但在最近一个窗口被封闭前不宜激进逆势；图3-55判例中收市价落在窗口3之下
    的X蜡烛线才是空头确认。
  tags: [principle, window, nison-revision, trend]
  task_ids: [task-07]
  source_location: 上书第七章图7.8/7.9；下书第3章图3-54~3-56

- id: p60
  title: 窗口与其他形态冲突时窗口优先
  type: rule
  source_chapter: 上书 · 第七章（并列形态实例）
  source_quote: |
    "在窗口与其他形态之间进行取舍时，我通常选择窗口。就本例而言，是要在看涨的锤子线和看跌的向下
    的窗口之间取舍。向下的窗口所造成的看跌前景优先于锤子线。市场必须收市于窗口之上，才能确认锤子线的看涨前景。"
  summary: |
    同理：突破趋势阻力线但下降窗口仍开着时不可做多（图3-50"烛光救险"）；流星线开启上升窗口时不可卖空，
    须等收市回到窗口下方。窗口是更强的趋势与支撑/阻挡定义者。
  tags: [rule, window, signal-priority]
  task_ids: [task-07]
  source_location: 上书第七章图7.20；下书第3章图3-49/3-50

- id: p61
  title: 岛形底的第一支撑取向上窗口而非岛形最低点
  type: rule
  source_chapter: 上书 · 第七章 窗口（岛形底）
  source_quote: |
    "我们得到的第一个支撑水平不是45.50（岛形底部的最低点），而是接近49.00的位置。这是受惠于该向上
    的窗口。……万一市场向下突破了窗口的支撑区域，我们自然要看下一个支撑水平，近乎45.50处。"
  summary: |
    蜡烛图相对线图的增量信息：窗口提供更贴近行情的支撑位，线图用户只能取岛形低点；两级支撑备援。
  tags: [rule, island-bottom, window, incremental-info]
  task_ids: [task-07]
  source_location: 上书第七章图7.7

- id: p62
  title: 窗口三天确认期（不必拘泥于"3"）
  type: rule
  source_chapter: 下书 · 第3章 窗口
  source_quote: |
    "某些日本交易员认为，如果窗口在三个交易时段内没有关闭，可以确认市场将朝窗口的方向发展。……
    我虽然不同意说得这么绝对，但等待三个交易时段来确认窗口的支撑或阻力我是深信不疑的。……如果窗口没有
    在两个、四个或者五个……交易时段内被封闭，也许仍可以认定窗口发出的行情持续信号有效。"
  summary: |
    判定口径：窗口开启后数个时段内收市价未封闭→持续性确认；"3"是文化偏好不是硬阈值。
  tags: [rule, window, confirmation-period]
  task_ids: [task-07]
  source_location: 下书第3章图3-53

- id: p63
  title: 高/低价位跳空突破：判据与失效条件
  type: rule
  source_chapter: 上书 · 第七章 高价位和低价位跳空突破形态
  source_quote: |
    "如果在一根坚挺的蜡烛线之后，出现了一群小实体的蜡烛线……缓解了市场所处的超买状态。一旦后来某一天
    的行情从这群小实体处打开了一个向上的窗口，就是看涨的信号。这就是一个高价位跳空突破形态。"
  summary: |
    急涨+小实体整固+同向窗口=看涨持续（急跌版反之）；摆动指数同步从超买回落至中性时更佳（超买缓解后再涨）。
    失效条件：收市于向上窗口之下（或向下窗口之上）。
  tags: [rule, gapping-play, invalidation]
  task_ids: [task-08]
  source_location: 上书第七章图7.13-7.17

- id: p64
  title: 并列阴阳线/并列白色线无须死记：窗口才是关键
  type: rule
  source_chapter: 上书 · 第七章 跳空并列形态
  source_quote: |
    "我们不必费劲记忆神秘的跳空并列阴阳线形态和跳空并列白色线形态到底是什么样式。窗口，才是关键因素。
    ……向下的窗口推动趋势向下，向上的窗口推动趋势向上，并且窗口分别构成阻挡或支撑区域。"
  summary: |
    尼森修订意见：窗口之后的蜡烛线颜色组合无关宏旨；向下跳空并列白色线虽为白线仍看跌（窗口定义趋势）。
  tags: [rule, tasuki, window-priority]
  task_ids: [task-08]
  source_location: 上书第七章图7.10-7.20

- id: p65
  title: 上升/下降三法判据（小实体2–5根、颜色不论、限长实体全部交易范围）
  type: rule
  source_chapter: 上书 · 第七章 上升三法和下降三法形态
  source_quote: |
    "这群小实体蜡烛线的理想数目是3根，但是2根或者3根以上也是可以接受的，条件是：只要这群小实体
    蜡烛线基本上都局限在前面长长的白色蜡烛线的高点到低点的价格范围之内。"……"从我的经验出发，2根，
    至多5根小实体都可以很好地完成形态。同时，小实体可以是任意颜色的。"
  summary: |
    判据要点：小实体限长实体"全部交易范围"（含影线，比孕线宽）；末根为坚挺长实体、开市高于前一日收市、
    收市创超越第一根的新高（下降三法反之）。风险报偿比短板：完成时价已远离低点，先算比值再决定。
  tags: [rule, three-methods, criteria]
  task_ids: [task-08]
  source_location: 上书第七章图7.21-7.30

```

## 七、长期形态（task-09）

```yaml
- id: p66
  title: 三山/三川/三尊形态：最后一峰（谷）须蜡烛信号确认
  type: rule
  source_chapter: 上书 · 第六章 三山形态和三川形态
  source_quote: |
    "在三山顶部形态的最后一座山的最高点，还应当出现一种看跌的蜡烛图指标（比如说，一根十字线，或者
    一个乌云盖顶形态等），对三山顶部形态做出确认。"
  summary: |
    三山=三重顶（波峰不必同高）；三尊=头肩形对等（日本早于西方约百年）；三川底必须收市向上突破形态
    最高水平才确认完成。颈线破位后按极性转换转为阻挡（图6.41-6.44）。
  tags: [rule, three-mountain, three-buddha, confirmation]
  task_ids: [task-09]
  source_location: 上书第六章图6.35-6.44

- id: p67
  title: 圆形顶部/平底锅底部必须以窗口确认；跳空再小也算数
  type: rule
  source_chapter: 上书 · 第六章 圆形顶部形态和平底锅底部形态
  source_quote: |
    "即便该跳空很小（即只有几美分），依然可以判定为向上跳空，因此证实了平底锅底部形态的完成。"
    "因为平底锅底部形态包含这个向上跳空（常规的圆形底部形态没有向上跳空），所以我认为平底锅底部形态
    比常规的圆形底部形态更重要。"
  summary: |
    平底锅底=圆弧底+向上窗口（市场"对坏消息免疫"）；圆弧顶对称要求向下窗口。塔形顶底则不需要跳空
    （两侧长实体即"塔"），完成偏晚、适合长线。
  tags: [rule, round-top, frypan-bottom, tower]
  task_ids: [task-09]
  source_location: 上书第六章图6.51-6.65

```

## 八、十字线族补充（task-10）

（p21–p24 已覆盖判读主线）

```yaml
- id: p68
  title: 十字线增强条件清单
  type: checklist
  source_chapter: 上书 · 第八章 神奇的十字线
  source_quote: |
    "1.后续的蜡烛线验证了十字线的反转信号。2.市场正处在超买状态或超卖状态。3.十字线在该市场出现得不多。
    如果在某个行情图上出现了许多十字线，则即使出现了新的十字线，也没有多大意义。"
  summary: |
    十字线作为重要反转信号（尤其顶部）的三个加权条件；与 p23 四问法配套使用。
  tags: [checklist, doji, weighting]
  task_ids: [task-10]
  source_location: 上书第八章开篇

```

## 九、趋势线与假突破（task-12）

```yaml
- id: p69
  title: 四类趋势线的蜡烛图画法（支撑线连下影线低点、阻挡线连上影线顶点）
  type: rule
  source_chapter: 上书 · 第十一章 蜡烛图与趋势线
  source_quote: |
    "在蜡烛图上绘制上升的支撑线时，把蜡烛线下影线的低点作为连接点。"……"在蜡烛图上绘制阻挡线时，
    方法是连接蜡烛线上影线的顶点。"
  summary: |
    四类：上升支撑线（常规）、下降支撑线（新低情形下的潜在支撑）、下降阻挡线（常规）、上升阻挡线
    （历史新高无可连高点时）。至少两点、三点更佳；蜡烛图信号在趋势线处的接触提供验证。
  tags: [rule, trendline, drawing]
  task_ids: [task-12]
  source_location: 上书第十一章图11.1-11.10

- id: p70
  title: 破低反涨/破高反跌完整交易规则（自带止损与目标）
  type: rule
  source_chapter: 上书 · 第十一章 破低反涨形态与破高反跌形态
  source_quote: |
    "最近的低点可以作为止损水平（最好以收市价为标准）。该破低反涨形态的价格目标要么是形态出现之前的
    行情高点，要么是之前横向交易区间的顶边。"
  summary: |
    破低反涨：跌破支撑收不回→收市回到支撑上方买入；止损=最近低点（收市价为准）；目标=前高点或区间顶边。
    破高反跌镜像。可单时段内完成；建议保守目标+备用目标双轨。量能配合（假突破缩量、回收放量）增强信号。
    机制=拿破仑"获胜的军队"：无力守住新低/新高的一方败退。
  tags: [rule, spring, upthrust, stop-and-target]
  task_ids: [task-12]
  source_location: 上书第十一章图11.11-11.17

- id: p71
  title: 极性转换原则：旧支撑变新阻挡、旧阻挡变新支撑
  type: principle
  source_chapter: 上书 · 第十一章 极性转换原则
  source_quote: |
    "过去的支撑水平演化为新的阻挡水平，过去的阻挡水平演化为新的支撑水平。这就是我所说的'极性转换原则'。
    ……这块技术分析的瑰宝并没有得到充分利用。"
  summary: |
    心理机制=开仓价位的情绪化关联（套牢盘解套抛售）；考验次数越多、横盘越久、越曾多次验证的价位，转换越彻底。
    应用：旧支撑被破即预挂新阻力卖出区；密集区破位后同理；箱体突破目标与极性转换并用互验。
  tags: [principle, polarity, s-r-conversion]
  task_ids: [task-13]
  source_location: 上书第十一章图11.18-11.25；下书图3-9/3-43、钥匙图8-16

```

## 十、百分比回撤（task-14）

```yaml
- id: p72
  title: 38%/50%/62%回撤位 + 不在裸回撤位买卖
  type: rule
  source_chapter: 上书 · 第十二章 蜡烛图与百分比回撤水平
  source_quote: |
    "最常用的是50%回撤水平，以及38%和62%的斐波那契回撤水平。"……"虽然百分比回撤水平可能演变成支撑
    或阻挡水平，但我并不建议在百分比回撤水平的位置买进或卖出，除非它还得到了蜡烛图信号的验证。"
  summary: |
    回撤位是潜在区域不是交易信号；须等蜡烛图信号（刺透、锤子线、长下影线群等）在回撤位出现才动手。
    毕玛时案例：50%回撤+极性转换+长下影线群三信号汇聚。
  tags: [rule, fibonacci-retracement, confirmation-required]
  task_ids: [task-14]
  source_location: 上书第十二章图12.1-12.5

```

## 十一、移动平均线（task-15）

```yaml
- id: p73
  title: 移动平均线五种用法
  type: checklist
  source_chapter: 上书 · 第十三章 移动平均线的用法
  source_quote: |
    "1.通过比较价格与移动平均线的相对位置，构成一个趋势指标……2.利用移动平均线构成支撑水平或阻挡水平……
    3.跟踪移动平均线波幅带（也称为包络线）……4.观察移动平均线的斜率……5.利用双移动平均线系统来交易。"
  summary: |
    收市价穿越均线=看涨/看跌信号；短均线下穿长均=死亡交叉（看跌），上穿=黄金交叉（看涨）；
    均线走平转下=看跌警讯；更长期趋势用40周/200天均线衡量。
  tags: [checklist, moving-average, usage]
  task_ids: [task-15]
  source_location: 上书第十三章

- id: p74
  title: 均线参数参考值（股票30/5天、期货40/65天）且非最优化
  type: calculation
  source_chapter: 上书 · 第十三章
  source_quote: |
    "在股票市场上，一般说来30天移动平均线和短期的5天移动平均线是一对良好的组合。在期货市场上，
    40天和65天移动平均线较为实用。它们的时间参数并不是按照最优化的要求选择的。今天最优的移动平均线，
    明天未必还是最优的。"
  summary: |
    缺失条件：参数为经验参考值，须在自己标的上验证；下书补充日本常用口径（短线5/9/25天，长线13周、26周、75天、200天）。
  tags: [calculation, moving-average, parameters, missing-conditions]
  task_ids: [task-15]
  source_location: 上书第十三章；下书第5章开篇

- id: p75
  title: 不裸按均线交易：均线信号必须经蜡烛图验证；均线阻挡下的底部信号会失败
  type: rule
  source_chapter: 上书 · 第十三章
  source_quote: |
    "我们不建议单纯从移动平均线……出发，完全根据移动平均线信号来交易。借助蜡烛图信号验证移动平均线
    的支撑作用或阻挡作用，然后再采纳其信号来动手建仓或平仓，这是极为重要的考虑。"
  summary: |
    图13.2反例：欧元在9天EMA压制下出现两个刺透形态+一个看涨吞没，均告失败——须等收市上穿均线才买。
    均线角色可转换：支撑失效后预期转为阻挡（图13.4）。
  tags: [rule, moving-average, confirmation-required, counter-example-supported]
  task_ids: [task-15]
  source_location: 上书第十三章图13.1-13.4

```

## 十二、摆动指数（task-16）

```yaml
- id: p76
  title: 摆动指数三用途与"积雨云vs下雨"分工
  type: principle
  source_chapter: 上书 · 第十四章 蜡烛图与摆动指数
  source_quote: |
    "摆动指数好似积雨云，但是我们需要从蜡烛图技术得到最终的确认信号才能下结论。于是，我们仅仅把
    摆动指数的超买或超卖状态看作警告信号，这是一条线索，此外还要观察是否出现了蜡烛图形态提供的最终验证。"
  summary: |
    三用途：①背离（价格新高而指数未新高=顶背离看跌；新低而指数未新低=底背离看涨）②超买超卖③运动力度
    （动量趋平=趋势减速）。超买卖极端值因市场而异（"您在自己的市场上测试"）。
  tags: [principle, oscillator, divergence, division-of-labor]
  task_ids: [task-16]
  source_location: 上书第十四章开篇；下书第5章差异指数同构

- id: p77
  title: RSI公式与70/30口径
  type: calculation
  source_chapter: 上书 · 第十四章 相对力度指数
  source_quote: |
    "RSI=100-100/(1+RS)，其中RS=该时段上涨价格累计幅度的平均值/该时段下跌价格累计幅度的平均值"
    "9天和14天，是最常用的两种时间参数。"……"当它高于70%时，表明市场处于超买状态……通常低于30%，则认为
    RSI反映了超卖状态。"
  summary: |
    inputs：收市价序列；formula如上；output：0–100。70/30为常用值非最优；背离与超买卖区叠加时信号更强；
    可对RSI作趋势线分析。
  tags: [calculation, rsi, threshold]
  task_ids: [task-16]
  source_location: 上书第十四章

- id: p78
  title: 随机指数公式与买入三条件（超卖+底背离+金叉）
  type: calculation
  source_chapter: 上书 · 第十四章 随机指数
  source_quote: |
    "（收市价-N天内的最低价）/（N天内的最高价-N天内的最低价）×100=%K"……"为了构成一个买入信号，需要满足
    以下三个条件：首先，市场必须处在超卖状态（随机指数的%D值为20%或更低）；其次，市场已经发生了正面相互背离
    现象；最后，慢%K线向上穿越了%D线。"
  summary: |
    慢%K=快%K的3期均线；%D=慢%K的3期均线。超买卖常用阈值80/20；14/19/21为常见参数。
    卖出三条件镜像（超买+顶背离+死叉）。与蜡烛图信号组合加权（图14.6/14.7）。
  tags: [calculation, stochastics, three-conditions]
  task_ids: [task-16]
  source_location: 上书第十四章

- id: p79
  title: MACD构成（12/26/9）与交叉信号
  type: calculation
  source_chapter: 上书 · 第十四章 MACD
  source_quote: |
    "第一条线是两条指数加权移动平均线的差值（通常采用12和26作为时间参数的两条指数加权移动平均线来
    计算）；第二条线是第一条差值线的指数加权移动平均线（通常用9作为时间参数）……称为信号线。"
  summary: |
    快线上穿信号线=看涨交叉，下穿=看跌交叉；MACD变化较慢，一般不用作短线工具；与蜡烛图信号互验时分量增加。
  tags: [calculation, macd, crossover]
  task_ids: [task-16]
  source_location: 上书第十四章

```

## 十三、交易量（task-17）

```yaml
- id: p80
  title: 相对量原则：不用绝对量，看相对增减与井喷
  type: rule
  source_chapter: 上书 · 第十五章 蜡烛图与交易量
  source_quote: |
    "因为不同市场的交易量数值各有其特点，差异较大，我们不采用绝对的交易量数值，而是采用相对的交易量。
    ……不论在哪个市场，我们观察的都是交易量的相对增减，尤其是交易量井喷的情况。"
  summary: |
    missing_conditions：相对量的基准（对比窗口）作者未给算法，须按个股自定。
    趋势方向上量能持续增长→趋势延续；量不再增长→趋势延续的依据不足。
  tags: [rule, volume, relative-volume, missing-conditions]
  task_ids: [task-17]
  source_location: 上书第十五章

- id: p81
  title: 理想量分布清单（形态×成交量配合）
  type: checklist
  source_chapter: 上书 · 第十五章；下书 · 第3章
  source_quote: |
    "在看涨的刺透形态中，我们一般预期其中黑色蜡烛线的交易量较轻，而白色蜡烛线的交易量较重。"……
    "在看跌吞没形态中，第一根蜡烛线（白色的）应当具有较小的交易量，而第二根蜡烛线（黑色的）应当具有较大的
    交易量。"
  summary: |
    核对清单：刺透黑轻白重；吞没前轻后重；理想上升三法首末两根长白酒线量最大；巨量窗口更坚实（窗口底边支撑
    更可靠）；看涨吞没前纺锤轻量、后长白酒线重量=反转马力加大；突破需放量验证。
  tags: [checklist, volume, pattern-confirmation]
  task_ids: [task-17]
  source_location: 上书第十五章图15.2/15.3/15.5；下书第3章图3-47

- id: p82
  title: 巨量十字线/纺锤线的两条判读小结
  type: rule
  source_chapter: 上书 · 第十五章
  source_quote: |
    "1.在过度延展的上涨行情之后，如果出现了一根带有不寻常的巨大交易量的十字线或纺锤线，则表明多头的
    驱动力被足够强大的供给所压制，上涨行情已经陷入停顿。这可能构成顶部反转。2.在陡峭的下降行情中，如果出现
    了一根带有超大交易量的十字线或纺锤线，则显示沉重的卖压已经被分庭抗礼的积极买压所抵消。"
  summary: |
    下降中的十字线平时不当作底部信号，但巨量+支撑区协同时必须重视（图15.4戴尔37.25美元）。
  tags: [rule, volume, doji, spinning-top]
  task_ids: [task-17, task-10]
  source_location: 上书第十五章图15.2/15.4

- id: p83
  title: 创新高而量缩=后继乏力警讯
  type: rule
  source_chapter: 上书 · 第十五章
  source_quote: |
    "当市场创新高的时候，我们更乐于看到交易量放大，从而验证价格变化。……虽然蜡烛线表现得牛气十足，
    但是其交易量太轻，将它的牛气打了折扣。……以这样的低交易量形成的上冲行情很可能后继乏力。"
  summary: |
    仅凭量缩不足以转空，但足以要求加小心并准备保护动作；随后长黑实体强化判断。
  tags: [rule, volume, new-high]
  task_ids: [task-17]
  source_location: 上书第十五章图15.6

- id: p84
  title: 巨量锤子线可更积极地收市买入
  type: rule
  source_chapter: 上书 · 第十五章
  source_quote: |
    "一根带有巨额交易量的锤子线，降低了市场回落到锤子线低点的可能性。因此，如果锤子线带有异常高的
    交易量，那么我们的态度可以更积极，更愿意在收市时买进；相比之下，如果锤子线的交易量没有发出相同力度的
    验证信号，那么我们的态度可能更为保守，倾向于等待更好的机会。"
  summary: |
    量能修正风险报偿比判断的范例：无巨量→等回踩；有巨量→收市直接买进的可接受度提高。
  tags: [rule, volume, hammer]
  task_ids: [task-17, task-20]
  source_location: 上书第十五章图15.1

```

## 十四、价格目标测算（task-18）

```yaml
- id: p85
  title: 价格目标≠支撑/阻挡：只用于平仓，不用于开新仓
  type: rule
  source_chapter: 上书 · 第十六章 测算价格目标
  source_quote: |
    "价格目标并不等同于支撑水平或阻挡水平。……我们不应当根据价格目标来建立新头寸，而是应当把已经
    持有的敞口头寸适当平仓。"
  summary: |
    到达目标只做止盈；开反向新仓须另有看跌蜡烛图信号或其他信号在目标位汇聚（目标位与阻挡重合时才可更进取）。
  tags: [rule, price-target, exit-only]
  task_ids: [task-18]
  source_location: 上书第十六章开篇

- id: p86
  title: 箱体突破目标测算：箱体高度投影
  type: calculation
  source_chapter: 上书 · 第十六章 箱体区间的突破信号
  source_quote: |
    "当行情推进到箱体顶部之上（属于看涨的突破信号）后，我们测量箱体区间的底部（支撑水平）到箱体区间的
    顶部（原先的阻挡水平）两者之间的竖直距离。……将A—B的箱体高度加到原先的阻挡水平上，推算突破后的价格目标。"
  summary: |
    inputs：箱体顶/底（收市价口径的突破确认）；formula：目标=突破位±箱体高度；看跌突破从支撑位减高度。
    失效条件：收市价重回箱体（同时按极性转换取得新阻挡确认）。
  tags: [calculation, box-range, measured-move]
  task_ids: [task-18]
  source_location: 上书第十六章图16.1-16.5

- id: p87
  title: 到达价格目标不能仅凭到位就买入
  type: rule
  source_chapter: 上书 · 第十六章（纳斯达克2750案例）
  source_quote: |
    "后来的价格运动低于2750的价格目标，因此价格目标并不必然构成支撑水平。这一点非常重要，值得仔细
    推敲。尽管纳斯达克综合指数跌到了2750，但是绝不能仅凭行情达到了价格目标便买入做多。"
  summary: |
    目标是统计性投影不是支撑；到位后仍须蜡烛图/极性转换等证据才可反向操作。
  tags: [rule, price-target, discipline]
  task_ids: [task-18]
  source_location: 上书第十六章图16.2

- id: p88
  title: 对等运动目标测算
  type: calculation
  source_chapter: 上书 · 第十六章 对等运动、旗形与尖旗形
  source_quote: |
    "如果市场先是猛力地上涨或下跌，继而对上述运动展开调整行情，那么最终当原先的行情恢复后，下一波
    行情运动至少应当与起初的猛力运动所形成的轨迹不相上下。"
  summary: |
    formula：目标=调整低点C+第一波（A→B）高度（看跌镜像）。构成三段：第一波→调整→第二波；
    调整幅度较旗形更深是对等运动与旗形测算的区别。
  tags: [calculation, measured-move]
  task_ids: [task-18]
  source_location: 上书第十六章图16.6/16.9

- id: p89
  title: 旗形/尖旗形目标：尼森保守算法（旗杆加到密集区底边）
  type: calculation
  source_chapter: 上书 · 第十六章 对等运动、旗形与尖旗形
  source_quote: |
    "看涨的旗形和尖旗形的价格目标计算方式是：先计算起初的急剧上涨行情（旗杆）从A到B的高度，然后把它
    加到密集区（旗形或者尖旗形均可）的底边上。更传统的做法是，把旗杆的高度加到旗形或尖旗形的顶边上。
    我宁愿错在过早地平仓退出，也不愿意错在精确追求最后那一哆嗦行情。"
  summary: |
    尼森偏离传统算法：看涨=旗杆加到底边（保守、早出），看跌=从密集区顶边减旗杆；与传统的顶边/底边口径并列记录。
  tags: [calculation, flag, pennant, conservative]
  task_ids: [task-18]
  source_location: 上书第十六章图16.7/16.8/16.10/16.11

- id: p90
  title: 上升/下降三角形目标测算：最宽处高度投影
  type: calculation
  source_chapter: 上书 · 第十六章（三角形）
  source_quote: |
    "从水平的阻挡线（A处）出发，算出三角形最宽处（B处）的垂直高度，加到刚刚被突破的阻挡水平上。"
  summary: |
    上升三角形=水平阻挡+依次抬高的低点，向上突破后投影；下降三角形=水平支撑+依次降低的高点，跌破后投影。
    破位后旧支撑/旧阻挡按极性转换取得新角色，可作行情受阻的验证。
  tags: [calculation, triangle]
  task_ids: [task-18]
  source_location: 上书第十六章图16.12/16.13

```

## 十五、止损与风险报偿比（task-20）

```yaml
- id: p91
  title: 初始交易时同时设定止损；止损是生意的成本；总有某个价位证明你是错的
  type: principle
  source_chapter: 上书 · 第四章 设置保护性止损指令的重要性
  source_quote: |
    "在初始交易时，就应该同时设定止损保护指令，此时交易者的态度最具有客观性。"……"要把止损当作这门
    生意的成本。"……"应该总是存在某个价位，表明我们是错误的。"
  summary: |
    止损是技术分析风险管理机制的核心；市场不留主观愿望余地、所有长期趋势都从短线开始。
    因止损退出=承认错误，"能及早查明自己的错误，是一种值得骄傲的能力"。
  tags: [principle, stop-loss, risk-management]
  task_ids: [task-20]
  source_location: 上书第四章止损节

- id: p92
  title: 形态隐含止损位清单（由形态与支撑客观给定）
  type: checklist
  source_chapter: 上书 · 第四/五/七章；下书 · 第4章
  source_quote: |
    "如果你根据这个形态进行放空操作，止损点就应该是乌云盖顶最高点的上方。"……"止损点（以收盘价为准）
    可以设定在锤子线低点的下方。"……"此前做多者则应该把止损卖出点设在缺口底部下方，在周收盘（即周五收盘价）
    到达该点位时卖出。"
  summary: |
    清单：乌云盖顶/看跌吞没高点上方（做空）；锤子线/启明星低点下方（做多，收市价为准）；支撑缺口底部下方
    （周收盘）；支撑水平/趋势线下方；破低反涨的最近低点。收市价破位才执行为普遍口径。
  tags: [checklist, stop-loss, pattern-implied]
  task_ids: [task-20]
  source_location: 上书第四/五/七/十一章；下书第4章图4-1~4-3

- id: p93
  title: 先算风险报偿比再下单：不划算就放弃（拉弓等放弦）
  type: principle
  source_chapter: 下书 · 第4章 风险与收益的权衡
  source_quote: |
    "请记住，在某个蜡烛图形态完成时，除非你判定风险与回报比率很诱人，否则请放弃交易。有句日本俗语
    所说的极是：'勇士的潜能是一张拉满的弓，但关键在于放弦的时机。'"
  summary: |
    判例（可可启明星）：买入1205、止损1169、目标1220→风险36对收益15，比值太低→放弃；一周后启明星低点
    成为支撑，上涨果然止于1220。信号成立≠交易成立；形态完成时价已走远（启明星/黄昏星/白三兵/上升三法）
    时尤其要先算后做。
  tags: [principle, risk-reward, pre-trade-check, core]
  task_ids: [task-20]
  source_location: 下书第4章图4-6；上书第四章图4.7（沃尔玛5美元风险案例）

- id: p94
  title: 巴菲特两条座右铭：保住本金，绝不忘记第一条
  type: maxim
  source_chapter: 上书 · 第四章 设置保护性止损指令的重要性
  source_quote: |
    "据说，著名的私人投资大家沃伦·巴菲特有两条座右铭：1.保住本金。2.绝不忘记第一条。"
  summary: |
    止损指令与第一条同义；"留得青山在，不怕没柴烧"；战术性撤退（"舍不得鱼钩，钓不着三文鱼"）。
  tags: [maxim, capital-preservation]
  task_ids: [task-20]
  source_location: 上书第四章止损节

- id: p95
  title: DISCIPLINE 交易守则清单
  type: checklist
  source_chapter: 上书 · 第二部分引言（市场永远不会错）
  source_quote: |
    "D——不要忘记过去的支撑水平和阻挡水平……S——始终采用止损指令作为保护措施……I——技术分析信号，
    越多越好（多技术方法共同参照原则）。N——绝不能带着'市场错了'的成见从事交易。E——注意研究市场对
    基本面信息的反应。"
  summary: |
    九条首字母守则（含 C 期权、I 日内图表、P 调整交易节奏、L 关注自营交易商动向）；期权两条为美国市场语境，
    其余七条可直接迁移。
  tags: [checklist, discipline, trading-rules]
  task_ids: [task-20, task-06]
  source_location: 上书第二部分引言脚注

- id: p96
  title: 做市场变色龙：一切预判必须可证伪，到达证伪价就改判
  type: principle
  source_chapter: 下书 · 第4章 做一个市场变色龙
  source_quote: |
    "只要你对行情形成了某个判断，就意味着你认为行情在某个时限内不会到达某个价位。如果行情恰恰在这段
    时间内达到了这一价位，就证明你的预测是错误的。"
  summary: |
    判例：看空原油者列出四重阻力（乌云盖顶高点、下降窗口、旧支撑转阻力、62%回撤），收市突破阻力区高点=
    判断被证伪→必须改看多。配套守则"市场永远不会错"：做趋势追随者不做趋势预测者。
  tags: [principle, falsifiability, adaptability, core]
  task_ids: [task-06, task-20]
  source_location: 下书第4章图4-11/4-12；上书第二部分引言"市场永远不会错"

```

## 十六、差异指数/偏离指数（task-21）

```yaml
- id: p97
  title: 差异指数与偏离指数公式及换算
  type: calculation
  source_chapter: 下书 · 第5章 差异指数 / 偏离指数
  source_quote: |
    "差异指数也称差异比率，用百分数表示，以收盘价减去移动平均值后的差除以所选定的移动平均值得出。"
    "偏离指数……由价格除以对应的移动平均值得出。……102%的偏离指数就相当于+2%的差异指数。"
  summary: |
    inputs：收盘价、选定均线；差异指数=(C-MA)/MA×100%，偏离指数=C/MA×100%（102%≈+2%）；
    output：百分比。两者形态完全相同，交易技术互通；超买卖=极端读数，中间状态=趋势方向判读，另有背离用法。
  tags: [calculation, disparity-index, formula]
  task_ids: [task-21]
  source_location: 下书第5章图5-3~5-7

- id: p98
  title: 超买超卖阈值须按标的自行测试（±10%起步口径）
  type: rule
  source_chapter: 下书 · 第5章 依据差异指数进行交易
  source_quote: |
    "13周差异指数如果到达+10%和-10%，就表明市场已经处于极端状态，可能发生反转。而在你自己的市场中，
    这个表示极端状态的差异指数峰值或谷底值有可能不是10%，而是别的数据，所以你应该进行反复测试。"
  summary: |
    ±10%为起点参考（图5-4股票案例）；标普期指13周差异指数案例用±2%（图5-5）。中间状态用法：指数上行=行情
    上行、下行=下行，可作趋势确认与背离监测。
  tags: [rule, disparity-index, threshold, self-testing]
  task_ids: [task-21]
  source_location: 下书第5章图5-4/5-5

- id: p99
  title: 日经偏离指数参考表与200日偏离>110%的牛尾提示
  type: calculation
  source_chapter: 下书 · 第5章 偏离指数
  source_quote: |
    "25日偏离指数为99%~104%（升势）……200日偏离指数为102%~110%……如果当前的200日偏离指数到达110%上方，
    可以认为市场处于过热状态，发生修正的概率就比较大。……处于过热状态的市场有可能正接近牛尾。"
  summary: |
    日经1980年代研究、2个标准差（95%概率）口径；升势/跌势分列25/75/200日区间。
    告诫：高偏离值不代表必然反转，只表明投机狂热；极端化过程中延续概率不断降低。年代久远，须以A股数据重估。
  tags: [calculation, deviation-index, reference-table, dated]
  task_ids: [task-21]
  source_location: 下书第5章参考表

```

## 十七、三线反向突破图（task-22）

```yaml
- id: p100
  title: 三线反向突破图画线规则（收盘价、新高新低才画线、三线反向突破画转向线）
  type: rule
  source_chapter: 下书 · 第6章 三线反向突破图的画法
  source_quote: |
    "如果某个收盘价超过前高，就画一条白线，如果收盘到达一个新低，就画一条黑线。如果收盘既没有创新高
    也没创新低，就不用画线。……只有当某个交易时段反向突破此前的三根连续白线（或黑线）时，我们才能画出一根
    反转线。"
  summary: |
    规则1–11要点：与基价/前一根线/此前极值比较；价格必须"超越"而非"触及"前高前低；三根连续同色线后，
    顺向只需创新高（低）即续画，反向须突破三线极点才画转向线（黑色转向线破三白酒线低点、白色转向线破三黑线高点）。
    独有优点：无需主观设定反转标准。
  tags: [rule, three-line-break, drawing]
  task_ids: [task-22]
  source_location: 下书第6章画法规则1–11、表6-1/图6-1

- id: p101
  title: 见白线买、见黑线卖；转向线作为平仓信号；黑白相间=无趋势
  type: rule
  source_chapter: 下书 · 第6章 三线反向突破图的交易技巧
  source_quote: |
    "三线反向突破图的基本交易原则是见白线买入，见黑线卖出。……许多交易者对此并不在意，因为他们认为
    只抓行情的主段，而不去找顶或找底，是更为安全的交易策略。"
  summary: |
    黑白相间=趋势不明；三根连续同色=趋势形成；转向线=基础性趋势转向信号。与蜡烛图分工：三线图定方向，
    蜡烛图找入场时机，转向线定平仓；熊市中的多头蜡烛图信号忽略或作平仓信号。
  tags: [rule, three-line-break, trading-system]
  task_ids: [task-22]
  source_location: 下书第6章图6-2~6-5

- id: p102
  title: 黑鞋/白套装/脖颈买入口诀与脖颈/黑套装/黑鞋卖出口诀
  type: rule
  source_chapter: 下书 · 第6章 黑鞋、黑白套装、脖颈
  source_quote: |
    "在脖子从黑鞋上方的白套装领口伸出来的时候买入。"……"交易者'应该在黑套装下面出现黑鞋时卖出。'"
  summary: |
    底部：小黑线（黑鞋，卖压衰竭）→白色转向线（白套装）→短白酒线（脖颈，确认）=买入。
    顶部：脖颈→黑色转向线（黑套装）→小黑鞋=卖出。黑鞋还提示对手仓位未回补/未派发的后续压力。
  tags: [rule, three-line-break, mnemonic]
  task_ids: [task-22]
  source_location: 下书第6章图6-11~6-13

- id: p103
  title: 线数选择：2–3线≈短均线、3–5线≈中均线、10线≈长均线
  type: rule
  source_chapter: 下书 · 第6章 其他突破图形
  source_quote: |
    "使用一线、二线、三线反向突破图，相当于使用相对的短期移动平均线。使用三线到五线突破图则相当于使用
    中期移动平均线，而十线突破相当于长期移动平均线。必须在长期、持续的尝试与验证中，我们才能发现自己究竟
    最适用哪种（几根线）突破标准。"
  summary: |
    反转标准越低敏感度越高、信号越多、拉锯越多；越高越迟钝、信号少但抓主段。三线最流行。
    纯经验映射，作者明言无最优化——须自测。
  tags: [rule, three-line-break, sensitivity, missing-conditions]
  task_ids: [task-22]
  source_location: 下书第6章图6-7~6-9

- id: p104
  title: 转向线后等待新线确认：确认越久出错越少、获利潜力越低
  type: rule
  source_chapter: 下书 · 第6章 对趋势反转的进一步确认
  source_quote: |
    "交易者对趋势反转的确认等待越久，出错的概率就越低，而获利潜力也会降低……'尽管推迟了启动，降低了
    利润，但出错的概率降低，安全因子增长。'"
  summary: |
    可选保守档：白色转向线后再等一根白酒线才买（黑镜像）；等价于使用更长均线——风险收益的正相关交换。
  tags: [rule, three-line-break, confirmation]
  task_ids: [task-22]
  source_location: 下书第6章图6-10

- id: p105
  title: 收盘价确认的代价与盘中试仓+收盘确认技法
  type: rule
  source_chapter: 下书 · 下篇引言 / 第6章
  source_quote: |
    "有些日本交易者会在盘中（而不是收盘）到达反转标准时先建立一个小头寸，然后等待收盘确认，如果收盘
    继续确认反转成立，他们就在收盘时加仓……如果收盘未确认反转，交易者就会了结此前建立的小头寸。"
  summary: |
    适用条件：新价图以收盘价为据、确认时价格可能已远离反转值。该技法隐含 T+0 环境（期货/美股），
    A股 T+1 下需变形（如尾盘临收市评估、次日开盘执行），属待核查的本土化缺口。
  tags: [rule, intraday-probe, closing-confirmation, t0-dependent]
  task_ids: [task-22]
  source_location: 下书下篇引言、第6章图6-3讲解

- id: p106
  title: 收益率序列的三线图口径：黑色转向线=买入信号
  type: rule
  source_chapter: 下书 · 第6章 三线反向突破图与趋势（收益率图）
  source_quote: |
    "在收益率三线反向突破图中，黑线是多头信号，因为收益率走低意味着价格走高。因此，这幅图上的黑色转向线
    为买入信号，而白色转向线为卖出信号，因为白色转向线意味着收益率高企，价格走低。"
  summary: |
    对国债收益率、基金净值收益率等反向序列的口径反转；适用于A股场外债基/理财净值曲线的判读。
  tags: [rule, yield-series, inversion]
  task_ids: [task-22, task-24]
  source_location: 下书第6章图6-6

```

## 十八、砖形图（task-23）

```yaml
- id: p107
  title: 砖形图画法：固定砖值、等高砖、不足预定值部分不显示
  type: rule
  source_chapter: 下书 · 第7章 砖形图的画法
  source_quote: |
    "如果行情沿着此前的方向继续前进，而且变动幅度达到一个预定的固定数值，我们就画一根新的砖形线
    （加一块新砖头）。"……"砖形图中各块砖头的大小是一样的。"
  summary: |
    与三线图的区别：有固定过滤值（如5点砖）且砖等高；行情变动必须"达到或超过"预定值才画新砖（非触及）；
    超出整数倍画多块砖，余额不显示。缺失条件：砖值须按波动率与标的价格自行选定。
  tags: [rule, renko, drawing, missing-conditions]
  task_ids: [task-23]
  source_location: 下书第7章画法规则1–6、表7-1

- id: p108
  title: 白砖买/黑砖卖；横盘拉锯期假信号频繁
  type: rule
  source_chapter: 下书 · 第7章 砖形图的交易技巧
  source_quote: |
    "白砖出现，就是买入信号；黑砖出现，就是卖出信号。只有当行情进入横盘整理时，砖形图才会导致频繁的进出。"
  summary: |
    砖形图交易规则最单一（唯一反转信号=换色砖）；趋势市抓主段、横盘市拉锯亏损（B1-S1类）——须先判趋势
    状态或配合蜡烛图/均线过滤。
  tags: [rule, renko, trading-system]
  task_ids: [task-23]
  source_location: 下书第7章图7-2~7-4

```

## 十九、钥匙图（task-24）

```yaml
- id: p109
  title: 钥匙图画法规则：转向值、顺向延伸不限幅度、穿越前高变粗/前低变细
  type: rule
  source_chapter: 下书 · 第8章 钥匙图的画法
  source_quote: |
    "如果价格继续沿着前一根线的方向行进，钥匙线顺着这个方向延伸，不管这个变动幅度的大小。"……
    "如果一根细线超越前高，从超越点位开始，线由细变粗，这个前高称为'肩'。"……"如果一根粗线向下跌破前低，
    这根线从前低被穿越的位置起由粗变细，这个前低称为'腰'。"
  summary: |
    规则1–11要点：反向变动须达转向值（且为收盘价）才右移画反向线（拐点线相连）；顺向延伸无需再达转向值；
    肩腰穿越触发阴阳（粗细）转换。多数用日/周收盘价，也可用日内分时。
  tags: [rule, kagi, drawing]
  task_ids: [task-24]
  source_location: 下书第8章画法规则1–11、表8-1/图8-1

- id: p110
  title: 见阳买入、见阴卖出 + 肩腰升降读势
  type: rule
  source_chapter: 下书 · 第8章 钥匙图的交易技巧
  source_quote: |
    "当钥匙线由阴转阳（由细变粗）时买入，当钥匙线由阳转阴（由粗变细）时卖出。"……"如果前后多个肩与腰
    节节抬高或逐级走低，则充分传达了市场的强势或弱势。"
  summary: |
    基本用法；横盘时同样拉锯。肩腰节节抬高=强势循环；腰低点跌破前腰=循环破坏的走弱第一个迹象；
    高低点逐级下移后首次低点上移=底部酝酿。
  tags: [rule, kagi, trading-system]
  task_ids: [task-24]
  source_location: 下书第8章图8-2~8-5

- id: p111
  title: 钥匙图双窗口形态：两腰夹一肩=底、两肩夹一腰=顶
  type: rule
  source_chapter: 下书 · 第8章 双窗口形态
  source_quote: |
    "在下行趋势中，市场发生反弹，形成一个肩部（S1），这个肩部的高点低于前一个腰部低点W1。后面一个腰部
    W2也高于肩部S1。……如果这两个腰部之间出现了不止一个肩部，这个形态还是可以被视为一个双窗口形态。"
  summary: |
    底部三步确认：见低点W1→比较后续肩群（最高肩低于W1）→肩群被突破且新腰W2仍高于最高肩。
    双窗顶镜像；多肩/多腰版本同样成立（关键是不触及对侧）。
  tags: [rule, kagi, double-window]
  task_ids: [task-24]
  source_location: 下书第8章图8-12~8-14

- id: p112
  title: 钥匙图多级突破：二级/三级突破作为进一步确认
  type: rule
  source_chapter: 下书 · 第8章 多级突破
  source_quote: |
    "在钥匙图中，这种等待意味着让钥匙线突破两个或两个以上的前高或前低，再来确认市场已经走强或者走弱。"
  summary: |
    一级突破=阴阳转换（基本信号）；二级/三级突破=额外确认，准确率提高、获利潜力降低（风险收益正相关）。
    三佛形态叠加二级突破时信号更强。
  tags: [rule, kagi, multi-level-breakout]
  task_ids: [task-24]
  source_location: 下书第8章图8-6/8-7、图8-19~8-21

- id: p113
  title: 钥匙线中点规则：修正不破前长线中点=强势
  type: rule
  source_chapter: 下书 · 第8章 修正发生在前钥匙线内部
  source_quote: |
    "如果市场上涨后发生修正，只要修正的低点没有触及前一根长长的钥匙线的中点，形态还是可以看多……
    注意，一般而言，中点的价值取决于这根钥匙线的长度，长度越大，这个位置的意义就越大。"
  summary: |
    上行修正止于前长线中点上方+再创新高=买入信号；下行反弹不过前长线中点+跌破前低=卖出信号；
    旧中点支撑失守后转为阻力（与蜡烛图实体中点同构）。
  tags: [rule, kagi, midpoint]
  task_ids: [task-24]
  source_location: 下书第8章图8-10/8-11、图8-25

- id: p114
  title: 百分比钥匙图：转向值随价格自动缩放（3%常用、5%长线）
  type: calculation
  source_chapter: 下书 · 第8章 百分比钥匙图
  source_quote: |
    "将转向值设定为一个百分比，而不是固定的绝对值。例如，在一个3%的钥匙图上，如果初始价为50美元，
    第一个转向值就是1.50美元。……随着股价上涨，转向值也自动上涨。"……"他个人的股票交易中通常使用3%的
    转向标准。对于相对长线的交易者而言，5%钥匙图也很受欢迎。"
  summary: |
    解决绝对值转向对低价股过高、高价股过低的问题；日本流行绝对值（手工画图），软件时代百分比更可行。
    3%/5%为参考，须自测。
  tags: [calculation, kagi, percentage-reversal]
  task_ids: [task-24]
  source_location: 下书第8章图8-2/8-7/8-17/8-20

- id: p115
  title: 钥匙线阴阳段长度比较判多空
  type: rule
  source_chapter: 下书 · 第8章 阴阳线的长度
  source_quote: |
    "只要比较一下钥匙线上粗（阳）细（阴）线的相对长度，我们就可以感觉到市场的主导力量究竟掌握在空方
    还是多方手中。如果阴阳线等长，我们可以视之为蜡烛图上的十字星，市场处于平衡状态。"
  summary: |
    阳段长=多方控制、阴段长=空方主导、等长=均衡；与蜡烛图长实体/十字星类比读势。
  tags: [rule, kagi, yin-yang-length]
  task_ids: [task-24]
  source_location: 下书第8章图8-8/8-9/8-25

- id: p116
  title: 新价图信号偏慢：不适合逃顶抓底，适合抓主段
  type: principle
  source_chapter: 下书 · 下篇引言 / 第8章
  source_quote: |
    "与三线反向突破图及砖形图一样，钥匙图不适合于及时逃顶或抓底，但对于喜欢抓住行情的'肉段'的
    交易者来说，它非常适合。"
  summary: |
    分工总则：新价图定方向与平仓时机（宏观），蜡烛图找入场时机（微观）；判例图8-17：镊子顶蜡烛图3月见顶、
    钥匙图4月确认。新价图也是只有收盘价的市场（共同基金、净值产品）唯一可用图形工具。
  tags: [principle, kagi, three-line-break, renko, division-of-labor]
  task_ids: [task-24, task-22, task-23]
  source_location: 下书下篇引言、第8章图8-17

```

## 二十、合成蜡烛与非标准形态（task-25）

```yaml
- id: p117
  title: 合成蜡烛线四步法
  type: rule
  source_chapter: 下书 · 第2章（图2-27）/ 术语解释
  source_quote: |
    "1.合成蜡烛线的开盘价即为这个蜡烛线形态中第1根蜡烛线的开盘价。2.合成蜡烛线的上影线的顶点，为
    这组蜡烛线中最高的那个高点……3.合成蜡烛线的下影线的低点，为这组蜡烛线中最低的那个低点……4.合成蜡烛线的
    收盘价，是这组蜡烛线中的最后一根蜡烛线的收盘价。"
  summary: |
    把多根形态合成为单根蜡烛判读多空（上影长实体小=空头排列等）；处理"长得不太标准"的形态的客观化辅助；
    与锚形图、方向形态分析并列的三种替代判读工具。
  tags: [rule, blended-candle, four-steps]
  task_ids: [task-25]
  source_location: 下书第2章图2-27、图3-17/3-23合成示范、图3-75

- id: p118
  title: 非标准形态三处理法（按标准等确认/位置加持/合成判读）
  type: rule
  source_chapter: 下书 · 第3章 启明星与主观性
  source_quote: |
    "将图形视为标准形态，判读其信号，然后等待市场的进一步确认。……如果某个非理想形态确认了一个支撑位
    或阻力位，或出现在严重超买或超卖区，形态构成反转信号的几率很大。……将这个形态组合成一根合成蜡烛线，
    然后看看这根合成蜡烛线给出的信号与这个形态的预测是否相符。"
  summary: |
    尼森处理非标准形态的成体系三法（M1/M2 启明星变体判例）；日本技术分析师协会的补充立场："竭力追求具体
    与精确……不如保留灵活性，以免挂一漏万"。
  tags: [rule, nonstandard-pattern, three-methods]
  task_ids: [task-25, task-06]
  source_location: 下书第3章图3-75讲解

```

## 二十一、心理与消息面（task-06 辅助）

```yaml
- id: p119
  title: 该涨不涨现象：市场对消息的反应比消息本身重要
  type: rule
  source_chapter: 下书 · 第2章（"不听邪"）
  source_quote: |
    "尽管中东发生战争，黄金却无法向上突破前高，这个该涨不涨的现象透露出明确的市场信号。注意：'该涨不涨'
    时，我们就必须绷紧警惕之弦。"
  summary: |
    利好不涨/利空不跌本身是强信号；不要在消息放出后立即交易，先观察市场反应再行动（巴鲁克："不是事件本身，
    而是对事件的人性反应"）。
  tags: [rule, news-reaction, reverse-theory]
  task_ids: [task-06]
  source_location: 下书第2章图2-1（1990黄金/中东战争）；上书第一章技术分析重要性第五点

- id: p120
  title: 远离传言困扰的市场
  type: maxim
  source_chapter: 下书 · 第2章（"不听邪"）
  source_quote: |
    "应该远离传言困扰的市场。牛顿曾说过：'我可以计算出天体的运行，但无法计算人的疯狂。'何必与疯狂纠缠呢？"
  summary: |
    日本人所谓"耳语战术"——散播假消息欺骗交易者；对以传闻驱动的个股（A股语境高发）为回避性规则。
  tags: [maxim, rumor, avoidance]
  task_ids: [task-06]
  source_location: 下书第2章

- id: p121
  title: 形态收录的校验规则：至少两个独立来源（三星形态唯一例外）
  type: principle
  source_chapter: 上书 · 第八章（三星形态）
  source_quote: |
    "在提出某种形态或信号之前，总是遵循一个校验规则：至少需要两个方面的独立信息来源证实同一个说法。
    这有助于确认那些行之有效的分析技巧，有助于避免大家都可能想象出来的成百上千似是而非的形状。"
  summary: |
    对其他蜡烛图资料来源保持审慎的方法论依据；三星形态仅凭一位日本交易员的单一来源收录，是作者自认的例外。
  tags: [principle, methodology, source-validation]
  task_ids: [task-10]
  source_location: 上书第八章三星形态节

- id: p122
  title: 数字"3"在蜡烛图技术中的地位（文化参数，参考标杆而非定律）
  type: principle
  source_chapter: 上书 · 第六章（数字"3"的重要性）；下书第3章
  source_quote: |
    "许多蜡烛图技术建筑在数字'3'的基础上。这反映了数字'3'在日本文化中具有重要意义。"
  summary: |
    白三兵、三只乌鸦、三山/三尊/三川、上升/下降三法、启明/黄昏星、三窗口、三天确认期皆与"3"相关；
    作者对"3"的口径多处申明为参考标杆（窗口三天、8–10个新高、±10%阈值同理），使用时须参数化并自测。
  tags: [principle, cultural-parameter, threshold]
  task_ids: [task-07, task-08, task-05]
  source_location: 上书第六章末节；下书第3章

- id: p123
  title: 长实体后的小实体序列=动量衰减预警
  type: rule
  source_chapter: 下书 · 第2章（高价区的长黑实体）
  source_quote: |
    "在长白实体（1）出现以后，又出现一系列实体很小的蜡烛线，它们表示，相对于长白实体（1）时期，
    市场的供需处于相对均衡状态，而长白实体（1）显示的是需求严重超过供应。"
  summary: |
    强单边（长实体）之后的小实体群/十字星/纺锤线=供需重新均衡，配合RSI超买即可预警顶部；
    其后长黑实体（至少为近期最长）确认控制权易手——"先前的涨幅越大，超买的情况越严重，这根长黑实体作为
    谨慎信号的可靠性就越强"。
  tags: [rule, momentum-decay, sequence]
  task_ids: [task-02]
  source_location: 下书第2章图2-17；上书第三章图3.8同构

- id: p124
  title: 底部愈宽，上升平台愈稳固；横盘愈久，密集区极性转换愈彻底
  type: principle
  source_chapter: 下书 · 第2章（图2-44）/ 第3章（图3-22）
  source_quote: |
    "在将近两个月的交易中，空头反复企图将价格打压在0.59美元以下，但均无功而返。一般来说，底部愈宽，
    上升平台便愈稳固。"……"横盘时间愈长，在这个价格区间参与买卖的交易者就愈多。……价格反弹到密集区时，
    很可能引发解套抛售。"
  summary: |
    时间维度规则：筑底时长与密集区时长决定支撑/阻挡的强度与极性转换的彻底程度；
    与 p71 极性转换、p03 位置原则配套。
  tags: [principle, base-width, congestion-zone]
  task_ids: [task-06, task-13]
  source_location: 下书第2章图2-44、第3章图3-22

```
