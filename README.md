# deepdive 归档仓

由 **爹助 (oneplusn-check)** 按 `oneplusn-test-1/agent_workflow#4` 的归档规范自动生成。

## 目录结构

| 文件夹 | 含义 |
|--------|------|
| `technical_element/` | 技术要素线索(八块腹肌:spec / skills / 知识 / 评测 / 设计 / 代码 clean / 测试 / 透明可审计) |
| `organization_element/` | 组织线索(AI-Native 组织、超级个体、新型研发模式等) |
| `company_element/` | 友商信息(Anthropic / OpenAI / Google 等) |
| `research_element/` | 学术界线索(新模型、新算法、新 Benchmark) |
| `custom_element/` | 客户线索(客户提的新需求、新想法) |

## 归档规则

- 每个 issue 一个 markdown 文件,文件名: `issue-<N>-<short-slug>.md`
- 一个 issue 可以归入多个文件夹(多技术线索时各放一份)
- 每份 markdown 含:标题 / 描述摘要 / 创建时间 / 技术线索分类 / 价值预估
- 价值预估三维:影响力 / 创新性 / 可复现性(各 1-5 分)
- 来源 issue 链接挂顶部,可溯源

## 维护方

爹助 (oneplusn-check) 在 `agent_workflow#4` 协作链下维护。新增 deepdive issue 后通过 cronjob 增量归档。
