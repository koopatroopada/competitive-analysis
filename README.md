# ⚔️ Competitive Analysis Master

> **Stop feature-table analysis. Start actionable competitive intelligence.**

一个专为 **AI 产品经理**和**战略决策者**设计的竞品分析 Skill。它不会给你一堆特征对比表，而是强制 AI 产出可执行的商业洞察。

## 🎯 这个 Skill 解决什么问题？

大多数竞品分析最终沦为“信息堆砌”——截了一堆图，搜了一堆数据，写了几十页 PPT，最后老板问一句：“所以呢？我们该怎么办？”如果你答不上来，那这几十页 PPT 就是无效的废纸。

**这个 Skill 的核心设计理念**：任何不产生结论的信息，都是噪音。它强制 AI：
- ✅ 每条洞察必须由 ≥2 条交叉验证的证据支撑
- ✅ 每条洞察必须映射到可执行的行动（test / copy / avoid / abandon）
- ✅ 禁止输出纯特征对比表
- ✅ 最终输出 ≤3 条关键洞察 + 带优先级和负责人的行动清单

## ✨ 核心特性

| 特性 | 说明 |
|------|------|
| 🚪 **硬性门槛** | 缺少任何必要条件时，AI 必须标记为 [UNVERIFIABLE HYPOTHESIS] |
| 🔍 **多源交叉验证** | 拒绝单一来源（尤其是官方营销文案），至少 2 条独立证据 |
| 📊 **多模型输出** | SWOT + Feature-Verdict Matrix，可选的波特五力 |
| 📝 **1 页结论驱动** | ≤3 条洞察 + 优先级行动清单（P0/P1/P2 + 负责人 + 成功指标） |
| 🎯 **聚焦 AI 产品** | 针对 AI 产品特别增加分析维度：模型边界、成本/延迟、数据飞轮 |

## 📦 安装

### 前置要求
1. **Node.js 18+** 和 **npm**
2. 支持 **Claude Code** 或 **Cursor** 等 AI 编程助手（Skills 系统在这些工具中可用）

> 💡 **如果你没有编程经验**，可以先完成基础环境配置：
> - [Linux 终端入门指南](https://lctt.x-cmd.com/202308/20230729%20Getting%20Started%20With%20Linux%20Terminal)
> - [Node.js 安装与环境配置教程](https://developer.baidu.com/article/detail.html?id=3589953)
> 
> 你需要熟悉终端（Terminal），在终端下载 npm，最好也学会用 nvm 管理不同版本的 Node.js，然后才能使用 npx 命令。

### 一键安装

在终端运行：

```bash
npx skills add koopatroopada/competitive-analysis
```

安装成功后，Skill 会被自动放到 `.claude/skills/` 目录下，AI 助手将自动获得此能力。

## 🚀 快速开始

安装后，在 Claude Code 或 Cursor 中直接对话，触发以下类型的需求：

### 触发场景

- “我们要不要进入 [某市场]？”
- “AI 视频剪辑的竞争格局是怎样的？”
- “竞争对手刚发布了新功能，我们该怎么办？”
- “帮我对 [某 AI 产品] 做一次完整的竞品分析”

### 使用示例

**输入**：
```
我们要不要进入 AI 会议纪要这个市场？帮我做竞品分析。
```

**Skill 工作流程**：
1. **澄清决策上下文** — 先问清楚：决策问题是谁决策的、输出格式是什么
2. **筛选竞品** — 扫描 App Store、行业报告、AI 社区，产出 3-4 个候选竞品
3. **用户确认** — 确保覆盖直接/间接/替代竞品三类
4. **定义分析维度** — 针对 AI 产品自动包含模型边界、成本/延迟、数据飞轮
5. **多源证据收集** — 从 ≥2 种来源交叉验证（公开数据、用户评论、实测、财报）
6. **应用分析模型** — SWOT + Feature-Verdict Matrix，可选波特五力
7. **产出 1 页报告** — 1 句话总结 + ≤3 条洞察 + 优先级行动清单（含负责人和成功指标）

## 📋 Skill 的硬性约束（HARD GATE）

以下任何条件缺失，AI **必须**要求澄清或标记为 `[UNVERIFIABLE HYPOTHESIS]`：

1. ✅ 明确该分析要回答的**决策问题**
2. ✅ 至少分类了 **3 类竞品**（直接/间接/替代）
3. ✅ 每条洞察有 **≥2 条证据来源** + 置信度标注
4. ✅ 每条洞察映射到 **一个可执行行动**（test / copy / avoid / abandon）

## 📄 项目文件结构

```
competitive-analysis/
├── SKILL.md          # 核心技能定义（YAML frontmatter + Markdown 指令）
└── README.md         # 本文档
```

## 📜 参考

本 Skill 的设计参考了以下文章：

- [竞品分析系列：竞品分析报告怎么写？](https://www.woshipm.com/share/6227779.html) — 竞品分析的核心方法论
- [如何写好一个 Skill 的实战总结](https://zhuanlan.zhihu.com/p/2018802513541907537) — Agent Skill 的编写技巧

