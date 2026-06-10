# Issue #5 — 【组织】微软等提出 SkillOpt:把 Skill 当成模型一样训练,GPT-5.5 平均提升 23.5 分

- **来源 Issue**: https://github.com/oneplusn-test-1/deepdive/issues/5
- **创建时间**: 2026-06-09
- **原始来源**: Hyman 的杂货铺
- **技术线索分类**: research_element(主)/ technical_element(副)

## 描述

微软研究院、上海交大、同济、复旦合作提出 SkillOpt:把 Agent 的「技能文档」当作可训练状态,用轨迹反馈、受控文本编辑(add/delete/replace)、验证集门控来优化技能,在不改模型权重、不增加部署期调用前提下让多模型/多执行环境稳定涨分。

核心机制:
- 训练对象从模型权重转向技能文本,目标模型冻结,优化器模型离线读轨迹提编辑建议
- 五步训练循环:跑任务→区分成败反思→受控文本编辑(有 learning rate 预算)→验证集严格涨分门控→拒绝编辑也记账
- epoch 级 slow/meta update 沉淀长期经验,只把简洁的 best_skill.md 交付部署
- 52 个评测单元(模型×benchmark×harness)全部最好或并列最好;SpreadsheetBench / OfficeQA 涨 ~39 分;支持跨模型/跨 harness(Codex⇄Claude Code)/跨 benchmark 迁移

## 价值预估

- **影响力**: ⭐⭐⭐⭐⭐ 直接对应"skill 工程"八块腹肌之一,为 skill 训练化提供完整工程框架
- **创新性**: ⭐⭐⭐⭐⭐ 把 reflection 改造成受控、可审计、可拒绝的训练循环,文本空间训练算法范式
- **可复现性**: ⭐⭐⭐⭐ 论文给出完整 pipeline 与超参,Hermes 的 skill 库可直接套用其门控/拒绝缓冲机制
- **跟进建议**: 强烈跟进。Hermes 自身的 skill 自我进化机制(check profile 已有 evolution cron)可参考 SkillOpt 的"严格涨分门控 + rejected buffer"重构,避免 skill 漂移
