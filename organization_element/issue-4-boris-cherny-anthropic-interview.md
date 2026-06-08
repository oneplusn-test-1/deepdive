# 【Claude】Claude Code 之父 Boris Cherny: "品味"不是人类护城河

- **来源 issue**: https://github.com/oneplusn-test-1/deepdive/issues/4
- **原文**: https://mp.weixin.qq.com/s/7xojGo-W7COYmWP3mxghOA
- **视频原版**: https://www.youtube.com/watch?v=RkQQ7WEor7w
- **创建时间**: 2026-06-07 12:55:54 UTC
- **技术线索分类**: `organization_element` (主) + `company_element`
- **受访者**: Boris Cherny — Anthropic Member of Technical Staff,Claude Code 核心建设者

## 核心论点

### 1. 品味不是最后的护城河

- 误区: 让 AI "做个设计"看第一个结果就说"没灵魂"
- 真相: 品味 = **设计评估标准 + 迭代机制 + 收敛能力**,这套能力 AI 也能学
- 真正稀缺的不是"拍脑袋决定",而是 **能写出优质评估标准的人**

### 2. 安全微调让模型变笨

- 每一轮后训练给模型加 1% 的"安全税"
- GPT-4o 刚发布时最强,几轮后训练后写作质量下降
- Claude Opus 4 也有类似问题
- → 启示: 模型上线后的迭代不是单调上升,会有"质量倒退"

### 3. 为什么还要招人? 招什么样的人?

CTO 们都在问"还需要招人吗"。Boris 答:

- 如果你的组织只是"代码搬运工" → 确实完了
- 但工程师价值在:
  - 懂用户
  - 深入业务逻辑
  - 知道每个阶段产品应承载什么功能
  - 系统性思考、参与"定义问题"

→ Anthropic 内部大量 Member of Technical Staff,无明确职级,鼓励轮岗(两周产品 / 两周基础设施)

### 4. "少招人,多给 token" — 反直觉建议

- 公司拿到融资马上招人 = 高隐性成本(管理 / 沟通 / 离职)
- token 是高弹性资源: 多花了换模型即可,几乎零调整成本
- → "保持最小规模的灵活性"

### 5. AI 编程下一步: 从代码交接 → 代码接管

- 当前: 工程师写大部分代码,调试 90% AI 做
- 未来: 代码初始生成 AI 主导,整块功能 AI 自主完成
- 关键边界: **核心安全程序你敢全交给 AI 维护吗?** — 这决定谁能继续留在牌桌
- Anthropic 内部排行榜: 谁让 Claude Code 提交的 commit 最多 — 第一名从 20% 升到 40% (本周)
- 下个阶段: 从 "Claude Code 写 Claude Code" → "Agents 管理 Claude Code 所有仓库"

### 6. 反对 promo packet 文化

- Boris 在 Google 时每季度 50-80 小时写晋升材料
- 这不是为了产品变好,是为了让老板觉得你好 — "影响力"的表演
- Anthropic 无职级 = 无 promo packet = 时间全在产品上

## 与 deepdive#2 (Fiona Fung) 的呼应

两人都强调:
- 别把组织看成"代码搬运工集合体"
- 工程师价值在懂用户 / 懂业务 / 定义问题
- 跨项目轮岗培养系统理解
- 主动削减 theater 流程(Fiona: 删会议;Boris: 删 promo packet)

→ Anthropic 内部对"AI-Native 组织"有 **一致且公开的对外叙事**,这是品牌护城河之一。

## 价值预估

| 维度 | 评分 (1-5) | 说明 |
|------|-----------|------|
| 影响力 | 5 | Claude Code 之父亲述,业界顶级信号源 |
| 创新性 | 4 | "少招人多给 token" + "品味=评估标准而非拍板"是反直觉新角度 |
| 可复现性 | 3 | "无职级 + 多 token" 难复制(组织文化深层依赖);但"评估标准是品味的真本质"可直接落到我们 agent 评测工程 |

**跟进建议**: 🟡 高 —— 与 #2 合并理解作为 AI-Native 组织实践参考。具体可落地的一点: 在我们 agent_workflow 里把"爹助的审查标准"系统化为可机读的 evaluation rubric,而非靠人类经验默会。这就是 Boris 所说的"把品味从拍板转化为评估标准"。
