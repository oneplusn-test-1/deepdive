# 【OpenAI】ChatGPT 与 Codex 官宣合体,10 亿人喜提"超级 Agent"

- **来源 issue**: https://github.com/oneplusn-test-1/deepdive/issues/1
- **原文**: https://mp.weixin.qq.com/s/nFBiJ7_yVzTq-Q3edr4_dg
- **创建时间**: 2026-06-03 02:46:20 UTC
- **技术线索分类**: `technical_element` (副) + `company_element` (主)
- **对应"八块腹肌"**: spec 工程 / skills 工程 / agent 评测工程 / 设计工程

## 技术要点(八块腹肌视角)

### 1. skills / agent 工程 — "角色插件"模式

Agent plugins 把"特定岗位需要的工具连接 + 领域知识 + 技能"打包为可调用模块。这本质是对 **skills 工程** 的工业化:

- 把"知识 + 工具 + 流程"封装成可复用单元
- 用户端只看到"角色"(数据分析师 / 创意 / 销售),底层是 skill 路由
- 对照我们(Hermes Agent)的 skills 体系: 已有 `agent-workflow-verification-report` / `agent-workflow-ops` 等,可对标 OpenAI 的"角色 → skills bundle"封装策略

### 2. spec 工程 — Annotations 选区批注

Annotations 把"需求 spec"从"整段文本"细化到"选区级":

- 选中表格区域 → 让 Codex 转图表
- 选中导航栏 → 改字体
- 选中报告结论 → 标信息来源

→ 本质是 **细粒度 spec 锚定**: 通过 UI 圈选,把模糊的"我想改这块"翻译成精准的 spec context,大幅减少多轮 prompt 推敲的成本。

### 3. agent 编排 — Sites 一句话造应用

Sites 让 Agent 可持续自主维护一个交互式 web 应用,实现"造好软件 → Agent 自动保鲜":

- 营销团队用 Sites 搭直播管理站点
- 财务预测 → 全公司仪表盘
- 产品计划 → 可运行原型

→ 对应 **agent 编排** + **透明可审计工程**: 产物从"一次性输出"升级为"持续维护的活产物"。

### 4. 评测 — token 效率新基准

GPT-5.5 同质量任务下 token 用量降至 1/3。这给"agent 评测工程"提出新维度: **同 quality 下的 token 经济性曲线**(质量横轴 / token 纵轴),而非单看 quality bench。

## 价值预估

| 维度 | 评分 (1-5) | 说明 |
|------|-----------|------|
| 影响力 | 5 | 把 agent 能力下沉到 ChatGPT 默认体验,改写"AI 装在哪儿"的范式 |
| 创新性 | 3 | 单点技术不新,组合 + 分发是新等级 |
| 可复现性 | 3 | "角色插件 + 选区批注 + 一句话造应用"三个模式都可在自家 agent 体系内拆解复用,关键是底层 skill 库和 IDE 集成度 |

**跟进建议**: 🟡 高优先级跟进 —— 重点观察 Plugins 的市场反馈,作为我们 skills 工程的产品化对标。
