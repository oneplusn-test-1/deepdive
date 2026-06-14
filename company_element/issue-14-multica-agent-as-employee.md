# Issue #14 — 【Multica】Multica:让 AI 智能体变为你的员工

- **来源 Issue**: https://github.com/oneplusn-test-1/deepdive/issues/14
- **创建时间**: 2026-06-11
- **原始来源**: 勇哥AI笔记
- **技术线索分类**: company_element(主)/ technical_element(副)

## 描述

Multica 是一个开源的 Managed Agents 平台,把 AI 编码 Agent 包装成"看板上的同事",支持任务分配、生命周期管理、跨 Agent 技能复用。相比 OpenAI 早先开源的 Symphony 只绑死 GPT 模型,Multica 兼容 Claude Code / Codex / OpenClaw / OpenCode / **Hermes** / Gemini / Pi / Cursor Agent 等多家 CLI。

核心设计理念:
- **Agent 即同事**:每个 Agent 有个人档案,出现在看板上,能评论、创建 Issue、报告阻塞
- **自主执行**:排队/认领/执行/完成/失败的完整生命周期,WebSocket 实时推送
- **可复用技能**:每个解决方案沉淀为团队级 skill 库
- **统一运行时**:一个控制台管所有算力(本地 daemon + 云端),自动发现 CLI 工具
- **多工作区**:Agent / Issue / 设置工作区级别隔离

安装: `brew install multica-ai/tap/multica` + `multica setup`,Web 端识别本地 Hermes 等 CLI 后即可分配任务。支持自部署模式。

## 价值预估

- **影响力**: ⭐⭐⭐⭐⭐ 直接对标本协作链(GitHub Issues + 多 Agent 假身份)的工程化产品形态,且原生兼容 Hermes
- **创新性**: ⭐⭐⭐⭐ "Agent 即同事 + 看板驱动 + 技能复用"三件套是 Loop Engineering 的成熟商业封装,但理念并非首创(本仓库已实践)
- **可复现性**: ⭐⭐⭐⭐⭐ 开源 + 已发布 + brew 一键安装,可立即对照本仓 SOUL/skills 体系做差异分析
- **跟进建议**: 强烈跟进。建议爹助单独立项做对照评估 — 重点看(1)Multica 的"Agent 档案 + 看板驱动"与本仓"Assignee = 指令"模型的兼容/冲突点;(2)它的 skill 复用如何沉淀;(3)是否值得迁移上去把 GitHub Issues 这层换掉。如评估通过,可显著降低协作链运维成本。
