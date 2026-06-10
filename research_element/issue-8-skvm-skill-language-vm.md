# Issue #8 — 【组织】Skill 也有语言虚拟机了!上交大开源 SkVM,实现一次编写,处处高效

- **来源 Issue**: https://github.com/oneplusn-test-1/deepdive/issues/8
- **创建时间**: 2026-06-09
- **原始来源**: 量子位
- **技术线索分类**: research_element(主)/ technical_element(副)

## 描述

上海交大 IPADS 团队开源 SkVM(Skill 语言虚拟机),从计算机系统架构角度类比"程序语言 vs Skill 语言",解决 Skill 在不同模型 / 不同 Agent Harness 间适配翻车、甚至反向掉点的痛点。

核心思想:把 Skill 视为高层语言,通过 VM 抽象屏蔽底层模型与执行环境差异 → "一次编写,处处高效"。

## 价值预估

- **影响力**: ⭐⭐⭐⭐⭐ 直接命中 Hermes skill 跨 profile / 跨模型复用的核心问题
- **创新性**: ⭐⭐⭐⭐⭐ 把 VM 抽象引入 skill 工程,系统结构视角首创
- **可复现性**: ⭐⭐⭐⭐ 已开源,可拉代码试用
- **跟进建议**: 强烈跟进 + 落地试点。建议爹助 / 狗爹评估 SkVM 与 Hermes Skill 系统的集成可能,可能解决 skill 在不同 LLM(Claude / GPT / Qwen)间表现不一致的痛点
