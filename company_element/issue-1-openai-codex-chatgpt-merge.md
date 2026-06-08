# 【OpenAI】ChatGPT 与 Codex 官宣合体,10 亿人喜提"超级 Agent"

- **来源 issue**: https://github.com/oneplusn-test-1/deepdive/issues/1
- **原文**: https://mp.weixin.qq.com/s/nFBiJ7_yVzTq-Q3edr4_dg
- **创建时间**: 2026-06-03 02:46:20 UTC
- **技术线索分类**: `company_element` (主) + `technical_element`
- **来源媒体**: 新智元

## 摘要

OpenAI 在 "Intelligence at Work" 发布会上宣布:未来几周内将把 Codex 装进 ChatGPT,合并为统一生态。Codex 周活已破 500 万(2 月以来 6 倍增长),知识工作者占比 20% 且增速是开发者的 3 倍。

三大升级:

1. **Agent plugins**: 首批 6 个"角色专属插件"(数据分析 / 创意 / 销售 / 产品设计 / 公开市场投资 / 投行),共接入 62 个企业应用、110 项技能。
2. **Annotations**: 直接在 Codex 输出(文档 / 表格 / 幻灯片)上选区批注,Agent 只改圈定部分,其余不动。
3. **Sites**: 一句 prompt → 可交互网页应用 + URL 分享,Agent 可持续自主维护。

底层引擎 **GPT-5.5**: 同质量任务下 token 用量降至约 1/3,把"智能门槛"压到最低。

## 战略意涵

- ChatGPT(近 10 亿 MAU)作为"分发层"是 OpenAI 对 Anthropic Cowork 的护城河式回击 —— Codex 变成 ChatGPT 默认能力,而不是单独 App。
- 同日 OpenAI Frontier 模型上架 AWS Bedrock,杀入 Anthropic 经营多年的 AWS 腹地。
- Dresser 引数据: AI 创造的经济价值 74% 被 20% 公司拿走,OpenAI 想掰回这个比例。

## 价值预估

| 维度 | 评分 (1-5) | 说明 |
|------|-----------|------|
| 影响力 | 5 | 近 10 亿 MAU 一夜获 Agent 能力,改变 AI Agent 分发格局 |
| 创新性 | 3 | Plugins / Annotations / Sites 三件套思路非首创(对标 Claude Cowork),但整合度和分发渠道是新等级 |
| 可复现性 | 2 | 受 ChatGPT 用户基数 + GPT-5.5 模型成本结构限制,我们短期不可能直接复制此战略;但 Plugins 的"角色化 + 工具收纳"模式可借鉴到内部 agent 编排 |

**跟进建议**: 🟡 高优先级,作为参照 —— OpenAI 的"角色插件 + 一句话造应用 + Agent 持续维护"是 AI-Native 工作流的标杆样板,值得对照评估我们自家 agent 工具栈是否需要补齐这三块。
