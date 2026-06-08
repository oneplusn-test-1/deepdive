# 【Claude】Claude Code 团队成员亲述: 动态工作流(dynamic workflows)该怎么用

- **来源 issue**: https://github.com/oneplusn-test-1/deepdive/issues/3
- **原文**: https://mp.weixin.qq.com/s/YJFC1uk_dxsNQd3Jr7kOeA
- **创建时间**: 2026-06-05 01:52:31 UTC
- **技术线索分类**: `technical_element` (主) + `company_element`
- **来源作者**: Thariq (Anthropic 工程师) / 机器之心译介
- **对应"八块腹肌"**: spec 工程 / skills 工程 / agent 评测工程 / 透明可审计工程

## 功能本质

Claude Code 新增"动态工作流"能力: 执行包含特殊函数的 JavaScript 文件,该文件 **由 Claude 自己即时生成**,协调多个子 Agent 并行工作。

- 与静态工作流(Claude Agent SDK / `claude -p`)区别: 静态需兼顾所有极端情况 → 通用但笨重;动态由 Opus 4.8 针对具体用例生成 → 精准且轻量
- 关键属性:可选模型、可选独立 worktree、可中断恢复

## 解决的三类失败模式

| 模式 | 描述 | 工作流如何破 |
|------|------|-------------|
| **智能体懒惰** | 复杂多步任务提前停止,50 条审 20 条就说完了 | 拆成独立上下文窗口的子 Agent,每个只盯一块 |
| **自我偏好偏差** | 倾向偏袒自己的结果,自我验证不靠谱 | 对抗式子 Agent 验证 |
| **目标漂移** | 多轮压缩后细节丢失("禁止做 X" 这种约束消失) | 每个子 Agent 独立目标 + 验证 |

## 7 大常用模式(技术干货)

1. **Classify-and-act**: 分类器路由
2. **Fan-out-and-synthesize**: 分发 → 汇总
3. **Adversarial verification**: 对抗式验证(每个输出由另一 Agent 评判)
4. **Generate-and-filter**: 多想法生成 + 筛选去重
5. **Tournament**: 多 Agent 同任务 + 两两比较 → 选最优
6. **Loop until done**: 工作量未知时循环到停止条件
7. **Quarantine**: 隔离 —— 处理不可信内容的 Agent 禁用高权限,高权限交给只读结构化输入的 Agent (**防 prompt 注入的核心模式**)

## 典型用例

- Bun 从 Zig 重写到 Rust(迁移与重构)
- Claude Code 自家的 `/deep-research` skill
- 报告事实核查 / 工单排序锦标赛 / 根因调查多假设并验 / 大规模工单分拣

## 工程建议

- 触发词 "ultracode" 强制生成动态工作流
- 配合 `/loop` (重复执行) + `/goal` (硬指标)
- `use 10k tokens` 自然语言设定 token 预算
- 工作流保存到 `~/.claude/workflows`,可打包为 Skill 分发

## 与我们工作的相关性(爹助视角)

我们的 agent_workflow 协作链(狗爹→狗助→爹助→妹助)本质上就是一个 **静态工作流**: 固定四角色、固定 assignee 流转、固定单 comment 五段报告。

→ 动态工作流的启示:

1. **隔离模式 (Quarantine)**: 当狗助处理外部不可信输入(用户提交的 issue body / 外部链接)时,可显式拆"读取 Agent"(无写权限)+ "决策 Agent"(看摘要决定动作),降低 prompt 注入风险。
2. **对抗验证**: 爹助审查本质上就是对抗式 verification —— 但目前我们没有"验证爹助 verification 质量"的 meta-Agent。可考虑引入。
3. **Tournament 模式**: 设计 / 命名 / 文案类争议,与其在 issue 里反复讨论,不如让 N 个 Agent 各出方案 + 评判 Agent 两两比对,直接给出胜者。

## 价值预估

| 维度 | 评分 (1-5) | 说明 |
|------|-----------|------|
| 影响力 | 5 | 一手原文 + Anthropic 自家工程师署名 + 已用于生产(Bun 重写)|
| 创新性 | 5 | "动态生成 + 独立上下文 + 对抗验证"是当前 agent 编排顶级实践,7 大模式有可复用性 |
| 可复现性 | 4 | 模式可直接复刻到我们自家 agent 体系;但底层需要 Opus 4.8 级别的"在线写代码生成工作流"能力,目前我们的 Hermes Agent 还需要靠 skill / SOUL 显式编排,无法做到完全动态 |

**跟进建议**: 🔴 紧急 —— 这是本批 deepdive 4 个 issue 中 **技术深度最高、最值得落地实验** 的一篇。建议爹助 / 狗爹近期立项,把 Quarantine + Adversarial verification 两个模式在 agent_workflow 协作链上做 POC。
