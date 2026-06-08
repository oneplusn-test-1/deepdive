# 【Claude】Claude Code 之父 Boris Cherny 访谈 — 友商视角

- **来源 issue**: https://github.com/oneplusn-test-1/deepdive/issues/4
- **原文**: https://mp.weixin.qq.com/s/7xojGo-W7COYmWP3mxghOA
- **创建时间**: 2026-06-07 12:55:54 UTC
- **技术线索分类**: `company_element` (副) + `organization_element` (主)
- **关联友商**: Anthropic
- **受访者**: Boris Cherny — Member of Technical Staff,Claude Code 核心建设者

## Anthropic 视角关键信号

### 内部使用数据(罕见披露)

- 内部排行榜: 用 Claude Code 提交 commit 最多者上榜
- 第一名 commit 比例: 几周前 20% → 本周 40%
- 第二名也接近 40%
- → **Anthropic 工程师有 ~40% 的代码由 Claude Code 提交**

### 路线图信号

- "从 Claude Code 自己开发 Claude Code(2025 已落地)→ 用 Agents 管理 Claude Code 所有仓库(今年晚些时候)"
- → Anthropic 在 **完整自主软件生命周期 agent** 这条路上节奏明确
- Boris 原话: "不仅仅是代码工具,更是产品开发与知识工作的中枢系统"

### 与 OpenAI Codex(deepdive#1)的对比

| 维度 | Anthropic Claude Code | OpenAI Codex |
|------|---------------------|--------------|
| 内部使用率信号 | 工程师 40% commit 来自 Claude Code | 未公开类似数据 |
| 下一步定位 | 全权限模式 + Agents 管理仓库 | 三大杀器(Plugins / Annotations / Sites)+ ChatGPT 集成 |
| 受众扩展策略 | 工程师 → 知识工作 | ChatGPT 10 亿 MAU 一夜赋能 |
| 信号源 | 工程师 IC(Boris) | 产品负责人(Embiricos)+ CRO(Dresser) |

→ Anthropic 的对外叙事 **主打"我们自己用得最深"**,OpenAI 主打"我们触达最广"。两种品牌护城河策略。

### 模型质量倒退披露(对友商监测有用)

Boris 直言:
- GPT-4o 刚发布时质量最强,后续多轮安全后训练后写作质量下降
- Claude Opus 4 也有类似问题
- → 启示: 评测友商模型时要 **区分发布初版 vs 当前版本**,不能只看 launch 时的 bench

## 价值预估

| 维度 | 评分 (1-5) | 说明 |
|------|-----------|------|
| 影响力 | 5 | Claude Code 之父亲述,Anthropic 路线图信号 |
| 创新性 | 3 | 多数观点 #2 Fiona 分享已覆盖,但"内部使用率 40% commit"是新数据点 |
| 可复现性 | 2 | 主要是观察信号,可借鉴的具体动作较少 |

**跟进建议**: 🟢 普通 —— 持续监测 Anthropic 公开披露的内部使用率数据,以及"Agents 管理仓库"产品的具体动作。
