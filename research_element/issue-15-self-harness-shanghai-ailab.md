# Issue #15 — 【PaperAgent】自优化的 Harness,才是好 Harness(Self-Harness)

- **来源 Issue**: https://github.com/oneplusn-test-1/deepdive/issues/15
- **创建时间**: 2026-06-12
- **原始来源**: PaperAgent(上海 AI Lab)
- **技术线索分类**: research_element(主)/ technical_element(副)

## 描述

上海 AI Lab 提出 **Self-Harness** — 不需人类工程师、也不需更强外部 Agent 介入,让固定 LLM 通过自身执行轨迹挖掘弱点并生成可验证的 Harness 修改提案的自优化范式。对比传统两种范式:
- Human Harness Engineering(人类手动) — 不可扩展
- Meta-Harness(强外部 Agent 优化弱 Agent) — 成本高 + 优化逻辑未必匹配目标模型

核心三阶段循环:
1. **Weakness Mining**:对失败轨迹做三维归因聚类(Verifier-level Cause / Causal Status / Abstract Mechanism),三维全一致才并簇,避免"症状相同病因不同"误判
2. **Harness Proposal**:固定模型 M 自己扮演 Proposer 角色,并行生成 N 个候选修改,每个修改必须锚定具体失败机制 + 最小化 + 附审计记录
3. **Proposal Validation**:回归测试门控,held-in 与 held-out 至少一个提升、另一个不退化才晋升 — 防局部过拟合

实验:Terminal-Bench-2.0(89 个容器化终端任务)。MiniMax M2.5 / Qwen3.5-35B / GLM-5 三款异构模型全部提升,Qwen3.5 从 15.1% 跃至 36.0%(initial harness 与模型严重错配),held-out 同步提升说明真正捕获可泛化执行机制。

## 价值预估

- **影响力**: ⭐⭐⭐⭐⭐ 直接对应"agent 评测工程 + skills 工程"两块腹肌,把 harness 优化从手工活变成自驱动循环
- **创新性**: ⭐⭐⭐⭐⭐ 三维失败聚类 + 同模型自 Proposer + 双 split 门控,是对 SkillOpt 思路的并行验证 + 强化(更严格的非退化门)
- **可复现性**: ⭐⭐⭐⭐ Terminal-Bench-2.0 公开,论文给出完整循环,Hermes 的 self-evolution cron 可立刻试点
- **跟进建议**: 强烈跟进。和 Issue #5 SkillOpt 一起组成"skill/harness 自训练"双子星,建议爹助以"双 split 门控 + rejected buffer"重写 hermes 自我进化 cron 的晋升规则,堵掉"看似有效但 held-out 退化"的回归风险。
