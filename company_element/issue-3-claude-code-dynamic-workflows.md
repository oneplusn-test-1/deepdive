# 【Claude】Claude Code 动态工作流(dynamic workflows) — 友商视角

- **来源 issue**: https://github.com/oneplusn-test-1/deepdive/issues/3
- **原文**: https://mp.weixin.qq.com/s/YJFC1uk_dxsNQd3Jr7kOeA
- **创建时间**: 2026-06-05 01:52:31 UTC
- **技术线索分类**: `company_element` (副) + `technical_element` (主)
- **关联友商**: Anthropic

## Anthropic 战略观察

继 Cowork 之后,Claude Code 持续把"agent 编排能力"产品化:

| 时期 | 产品动作 | 战略意图 |
|------|---------|---------|
| 早期 | Claude Code(单 Agent CLI) | 开发者工具,建立护城河 |
| 中期 | Claude Agent SDK / `claude -p` | 静态工作流,程序化编排 |
| 现在 | Dynamic Workflows | 由模型自己生成编排代码,**降低非技术用户使用门槛** |

→ Anthropic 在 "agent 编排" 这条线的产品演进非常清晰: **从程序员到知识工作者,从静态到动态**。

## 与 OpenAI Codex(deepdive#1)对照

| 维度 | Anthropic Claude Code | OpenAI Codex |
|------|---------------------|--------------|
| 用户基数 | 较小但忠诚度高(开发者口碑) | 借 ChatGPT 一夜 10 亿 MAU |
| 编排深度 | 动态工作流 + 7 大模式 + Quarantine 等模式库,**深度强** | Agent plugins(角色化封装),**广度优先** |
| 产品形态 | CLI + Skill 包 | ChatGPT 内嵌 + 桌面 + Excel/Slack/PPT 集成 |
| 差异化 | 工程师 / agent 编排专家市场 | 通用知识工作者市场 |

→ 这是经典的 **深度 vs 广度** 路线之争。Anthropic 押注"agent 编排能力的天花板",OpenAI 押注"agent 触达的最大化"。

## 价值预估

| 维度 | 评分 (1-5) | 说明 |
|------|-----------|------|
| 影响力 | 4 | 一手技术细节,工程师社区影响大;但相对 OpenAI Codex 公关声量较小 |
| 创新性 | 5 | 动态生成工作流 + 7 大模式是当前 SOTA |
| 可复现性 | 3 | 7 大模式可学;但"模型自己写编排代码"需要 Opus 4.8 级别底模 |

**跟进建议**: 🟡 高 —— 持续观察 Anthropic 在 "agent 编排" 这条护城河上的迭代节奏,与 OpenAI Plugins 体系形成对比分析。
