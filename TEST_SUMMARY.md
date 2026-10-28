# Stage 4 压力测试摘要

本文件汇总本包的压力测试材料与实测结构检查结果。通过情况一律引自根目录 `test-results.md`（评分日期 2026-10-11），未做二次评分，也没有把「未记录」写成「通过」。

## 测试范围

**被测对象**：27 个规范能力单元（C01–C27），编译为两种分发形态。

| 形态 | 可发现入口 | 内容 |
|---|---|---|
| single | 1 个（`jp-candlestick-analysis-skill`） | 入口 + 27 张能力卡 + 索引 / 速查 / 术语 / 概览 |
| pack | 6 个（1 个路由入口 + 5 个晋级 Skill） | `jp-candlestick-analysis-skill-router`（带 27 卡）、`stop-reward-risk-skill`、`price-target-retracement-skill`、`window-gap-management-skill`、`support-resistance-system-skill`、`kagi-chart-skill` |

**触发用例**：7 个 `test-prompts.json` 文件，共 72 条记录。其中 `pack/jp-candlestick-analysis-skill-router/` 的 11 条是入口用例的副本（pack 模式下入口由 router 承担），去重后为 6 套独立用例、61 条。

| 文件（所在 skill） | should_trigger | should_not_trigger | edge_case | 合计 |
|---|---|---|---|---|
| `single/jp-candlestick-analysis-skill` | 5 | 3 | 3 | 11 |
| `pack/jp-candlestick-analysis-skill-router`（入口用例副本） | 5 | 3 | 3 | 11 |
| `pack/kagi-chart-skill` | 4 | 3 | 3 | 10 |
| `pack/price-target-retracement-skill` | 4 | 3 | 3 | 10 |
| `pack/stop-reward-risk-skill` | 4 | 3 | 3 | 10 |
| `pack/support-resistance-system-skill` | 4 | 3 | 3 | 10 |
| `pack/window-gap-management-skill` | 4 | 3 | 3 | 10 |
| **合计（7 个文件）** | **30** | **21** | **21** | **72** |
| **去重后（6 套独立用例）** | **25** | **18** | **18** | **61** |

类型覆盖：`should_trigger` / `should_not_trigger` / `edge_case` 三类齐备，`output_case` 0 条（触发用例文件里不设该类）。输出评测（27 单元 × normal / boundary = 54 个场景）的任务与断言文件不在本仓库内，其逐项评分结论见根目录 `test-results.md`。

另有无卡对照 5 组（C20 / C16 / C11 / C15 / C25 的 normal 场景），用于衡量「带卡」相对基线的增量。

## 结构检查

以下为本次逐项实测（不是照抄旧记录）：2026-10-29 用脚本遍历仓库实测——逐个 `json.load` 校验 JSON、统计 `test_cases` 长度与 `type` 分布、按目录清点 `SKILL.md` 与能力卡六段。

- **JSON 可解析性**：仓库内 7 个 `test-prompts.json`（`single/` 1 个 + `pack/` 6 个）逐个用 `json.load` 解析，全部可解析，顶层键均为 `skill` / `version` / `test_cases`；另有 3 个构建清单 JSON（`pack/BUILD_MANIFEST.json`、`pack/capability-destinations.json`、`single/.../BUILD_MANIFEST.json`）同样可解析。
- **frontmatter**：7 个 `SKILL.md`（single 1 个 + pack 6 个）首行均为 `---`，YAML frontmatter 齐全。
- **六段完整性**：`single/.../references/capabilities/` 与 `pack/.../references/capabilities/` 各 27 张卡，R / I / A1 / A2 / E / B 六段无缺失；pack 下 5 个单文件 `SKILL.md`（单文件即完整能力卡）六段同样完整。
- **候选层**：`candidates/` 5 个文件（frameworks / principles / cases / counter-examples / glossary）合计 440,872 字节，对应阶段 1 的 331 条候选（框架 45 + 原则 124 + 案例 40 + 反例 35 + 术语 87）。
- **未做的检查**：本包未附独立的 lint 或 schema 校验脚本，上述结论来自本次解析与文本比对，不是自动化回归。

## 结果

- **skills: 27**（能力单元 C01–C27）；可发现入口 7 个（single 1 + pack 6）
- **test_json: 7** 个 `test-prompts.json`（`single/` 1 个 + `pack/` 6 个），合计 72 条记录（`should_trigger` 30 / `should_not_trigger` 21 / `edge_case` 21 / `output_case` 0）；去重后 6 套独立用例、61 条（`should_trigger` 25 / `should_not_trigger` 18 / `edge_case` 18）
- **通过情况**（引自根目录 `test-results.md`）：
  - 触发：`should_trigger` 25 / 25、`should_not_trigger` 18 / 18；`edge_case` 18 条中 15 条直接通过、2 条由路由入口以正确行为承接（记为可接受偏差）、1 条（stop-reward-risk-skill edge-03 混合请求被整体拒答）修 skill 后待复测
  - 输出：首轮 52 / 54 场景 PASS（断言 252 / 255，98.8%），C24（砖形图）与 C25（钥匙图）两个 FAIL 经回炉修卡后回归，最终 54 / 54 场景 PASS
  - 判停：`judge_stop` 38 / 38（记录口径），24 个 boundary 场景全部真判停 / 追问 / 拒答
  - 无卡对照：5 组完成，其中 4 组卡增量「中等偏有限」，C25 一组基线首段反超卡版——正是修卡的直接证据
- **口径差异（如实标注）**：`test-results.md` 记断言总数 255（C01–C14 文件 140 条 + C15–C27 文件 115 条）、`judge_stop` 38 条。生成期的 `output-tasks__*.json` 与 `output-assertions__*.json` 已不在本仓库内，本次无法对这两个数字做二次核验，因此本文件只引用 `test-results.md` 的记录值，不另行给出「实测断言数」，也不据此改写通过率。可复算的部分（触发用例的文件数、用例数、类型分布、JSON 可解析性）已在本文件上半部分按实测重写。

## 可接入 darwin-skill 的后续动作

1. **触发用例转回归样本**：61 条独立用例已按 skill 归位到各自目录的 `test-prompts.json`（`single/` 1 份 + `pack/` 6 份，其中 router 一份为入口用例副本），`should_trigger` 与 `should_not_trigger` 成对使用，专防改 description 后的误触发；18 条 `edge_case` 是跨技能混淆诱饵，适合挂到路由入口做回归。
2. **输出场景转评分卡**：54 个场景 + 255 条断言（`test-results.md` 记录值）可直接落成 darwin 的评分项；`number` 类按容差比对，`must_not_include` 只判实质违规（否定性提及不判违规），`judge_stop` 单列一档。
3. **保留两处已修缺陷的原题**：renko 反向砖起算、kagi 前高/前低取位，两题必须留在回归集里，防止卡修订后退化——它们是本包唯一被证实的判据歧义。
4. **接入顺序建议**：先跑触发（快、无外部数据依赖）→ 再跑 24 个 boundary 判停（考察是否硬给结论）→ 最后跑 normal 输出评测（需逐项复算，成本最高）。
5. **用无卡对照当基线**：5 组对照记录可作为「卡修订是否真的带来增益」的参照；若改卡后增量仍为「中等偏有限」，应如实记录而非包装成显著提升。
