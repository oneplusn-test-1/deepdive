# Issue #17 — 【智源】2026 智源大会热议 Agent 最前沿趋势:从会执行到会进化

- **来源 Issue**: https://github.com/oneplusn-test-1/deepdive/issues/17
- **创建时间**: 2026-06-13
- **原始来源**: 智源社区(2026 智源大会"终端智能体与 OpenClaw" + "AI 自进化"两个论坛综述)
- **技术线索分类**: research_element(主)/ technical_element(副)

## 描述

2026 智源大会两场 Agent 论坛同期召开,呈现 Agent 技术的两面镜子:
- **终端智能体与 OpenClaw 论坛**(刘知远主持):讨论 Agent 如何通过 Harness 连接模型、工具、环境、记忆、符号结构、安全沙箱、端云系统,从"会响应"变成"能持续执行任务"
- **AI 自进化论坛**:讨论 Agent 如何从交互/失败/探索/反馈中形成记忆、规则、世界模型、持续学习能力

核心观点:
1. **OpenClaw 的路标意义**(林衍凯):没有发明底层技术,但第一次把模型/Skill/记忆/接口/入口组织成大众可感知的形态 — 类比浏览器之于互联网
2. **Harness = Model + Harness 公式**(李元春):终端 Agent 时代,Harness 比模型更接近产品成败分水岭。Coding Agent 进展快是因为代码世界有数据 + 清晰环境 + 可验证奖励;GUI/Mobile Agent 面对的混乱现实需要专门工程
3. **Organization Model**(钱忱):让组织变得可生成 — 组织也是一种可被 LLM 建模的对象
4. **Neuro-Symbolic Agent**(郭兰哲):从反应式决策走向可验证决策
5. **Environment = Missing Data**(范文栋,CAMEL):Agent 的训练数据瓶颈不是 prompt,是环境
6. **百度 DuMate / 腾讯 Work Buddy / 网易有道**等产业落地报告
7. **智源-面壁联合加速器**发布

讨论核心:谁会定义 Agent 时代的"操作层"— 谁管模型调用 / 调度工具 / 存储记忆 / 连接设备 / 划定安全边界 / 成为用户默认入口。

## 价值预估

- **影响力**: ⭐⭐⭐⭐⭐ 国内 AI 学界 + 头部产业(刘知远 / 林衍凯 / 钱忱 / 段亦涛 / 李景秋 / 汪晟杰)一次性集结,信号强度极高
- **创新性**: ⭐⭐⭐⭐ "Agent = Model + Harness" + "Environment is Missing Data" + "Organization Model" 三个公式提供清晰研究坐标系
- **可复现性**: ⭐⭐⭐ 综述类内容,具体技术需追溯各报告原文/论文
- **跟进建议**: 强烈跟进。"Agent = Model + Harness"已成共识,本仓 SOUL/skills/cron 三层栈正是 Harness 工程实例。建议爹助单独立项把"操作层定义权"映射到本协作链:Hermes 作为运行时、GitHub Issues 作为看板、SOUL 作为身份 — 对照林衍凯的判断查缺漏。同时"Environment is Missing Data"提示我们 deepdive 仓本身就是 Hermes 的 environment 数据库,应加大归档强度。
