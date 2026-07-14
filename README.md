---
<div align="center">
  <h1>JTBD Innovation OS </h1>
  <p><strong>企业级 AI 用户洞察与产品创新操作系统</strong></p>
  <p>基于 Jobs-to-be-Done 2.0 方法论的 Multi-Agent 产品创新工作流</p>
  <p>
    <img src="https://img.shields.io/badge/version-4.0.0-blue.svg" alt="版本 4.0.0">
    <img src="https://img.shields.io/badge/status-active-brightgreen.svg" alt="状态: 活跃">
    <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="许可证: MIT">
  </p>
</div>

---

## 📖 项目简介

**JTBD Innovation OS ** 是一个完整的 Multi-Agent 产品创新操作系统，能够将原始用户声音转化为可执行的商业创新决策。

> People do not buy products. They hire products to make progress.

该操作系统覆盖从用户数据收集到 GTM 策略的完整闭环，包含 17 个专用 Agent、14 个 JTBD 方法论框架、4 个验证器脚本和 12 个输出模板。

---

## 🎯 适用人群

| 角色 | 使用场景 |
|------|----------|
| 产品经理 | 用户研究分析 -> 需求定义 -> PRD 生成 -> 产品路线图 |
| 用户研究员 | 访谈数据处理 -> 用户洞察提取 -> JTBD 提炼 -> 验证报告 |
| 创新团队 | 机会识别 -> 概念生成 -> 概念验证 -> GTM 策略 |
| 创业者 | 用户需求发现 -> 产品定义 -> MVP 规划 |
| 增长团队 | 用户行为分析 -> 切换动因识别 -> 改进机会排序 |

---

## 🏗️ 核心架构

系统分为 9 个层级，自底向上逐步从原始数据推导到商业执行：

`
用户数据
   ↓
Layer 0  数据理解  -> 数据质量评估、用户说法 vs 行为观察
   ↓
Layer 1  用户理解  -> 用户画像构建、情景分析
   ↓
Layer 2  行为分析  -> 切换行为分析、Four Forces 分析
   ↓
Layer 3  Job 发现 -> JTBD 提炼、Job Hierarchy、Job Map
   ↓
Layer 4  需求定义  -> 需求分类、Desired Outcome 工程
   ↓
Layer 5  验证      -> 证据验证、5T 原则检查
   ↓
Layer 6  创新决策  -> 机会评分与优先级排序
   ↓
Layer 7  产品创新  -> HMW 概念生成、用户验证计划
   ↓
Layer 8  商业执行  -> 产品路线图、GTM 策略
`

### Agent 模块总览

| Layer | Agent | 核心输出 |
|-------|-------|----------|
| 0 | Data Quality Agent | 数据质量报告 |
| 0 | Observation Agent | 用户言行差异分析 |
| 1 | Persona Agent | 用户画像 |
| 1 | Context Agent | 情景地图 |
| 2 | Switch Agent | 切换分析报告（时间线 + Four Forces） |
| 3 | JTBD Agent | JTBD 陈述 |
| 3 | Job Map Agent | 8 步任务流程地图 |
| 4 | Need Agent | 需求分类（Pain/Benefit） |
| 4 | Outcome Agent | Desired Outcome 陈述 |
| 5 | Evidence Validation Agent | 验证报告 + 5T 检查 |
| 6 | Opportunity Agent | 机会评分排序 |
| 7 | Product Translation Agent | 需求 -> 特性 -> 用户故事 |
| 7 | Concept Agent | 概念卡片（HMW） |
| 7 | Validation Agent | 用户验证计划 |
| 8 | Roadmap Agent | 三阶段产品路线图 |
| 8 | GTM Agent | 上市策略 |

---

## 🚀 快速开始

### 安装

该 Skill 设计为 Codex 平台的自发现 Skill。安装到 Codex Skills 目录后，当用户输入与用户研究、产品创新、JTBD 分析相关的任务时自动触发。

`ash
# 克隆到 Codex Skills 目录
git clone https://github.com/your-org/jtbd-innovation-os.git ~/.codex/skills/jtbd-innovation-os
`

### 基本用法

将用户研究数据（访谈记录、调查数据、CSV、Excel、PDF、TXT）提供给 Codex，触发该 Skill 后自动执行完整分析流程。

**支持的输入格式：**

| 格式 | 说明 | 示例 |
|------|------|------|
| 访谈记录 | 原始访谈文本，支持中英文 | 用户访谈逐字稿 |
| CSV | 结构化用户数据 | 调研问卷结果 |
| Excel (.xlsx/.xls) | 表格数据 | 用户反馈汇总表 |
| PDF | 文档格式研究报告 | 用户研究报告 |
| TXT | 纯文本数据 | 用户评论、反馈集 |

**支持的语言：** 中文、英文、中英混合

---

## 📂 项目结构

`
jtbd-innovation-os/
├── SKILL.md                        # 主入口：Skill 元数据与工作流定义
├── README.md                       # 本文件
├── config/                         # 配置文件
│   ├── workflow_config.yaml        # 工作流编排规则与分支决策
│   ├── scoring_config.yaml         # 7 维机会评分参数配置
│   └── output_schema.yaml          # 结构化输出字段定义
├── agents/                         # Agent 模块（17 个）
│   ├── data_quality_agent/         # 数据质量评估
│   ├── observation_agent/          # 用户言行观察
│   ├── persona_agent/              # 用户画像
│   ├── context_agent/              # 情景分析
│   ├── switch_agent/               # 切换行为分析
│   ├── jtbd_agent/                 # JTBD 提炼
│   ├── job_map_agent/              # Job 流程地图
│   ├── need_agent/                 # 需求分类
│   ├── outcome_agent/              # Desired Outcome 工程
│   ├── evidence_validation_agent/  # 证据验证
│   ├── opportunity_agent/          # 机会评分引擎
│   ├── product_translation_agent/  # 产品翻译
│   ├── concept_agent/              # 概念生成
│   ├── validation_agent/           # 验证计划
│   ├── roadmap_agent/              # 路线图规划
│   └── gtm_agent/                  # GTM 策略
├── frameworks/                     # JTBD 方法论参考文档（14 份）
├── validators/                     # Python 验证脚本
├── templates/                      # 结构化输出模板
└── examples/                       # 完整案例研究（4 份）
`

---

## 🧠 JTBD 方法论核心原则

### 什么是 Job？

**Job** 是用户在特定情境下想要达成的进展（Progress）。它有三个维度：

- **功能维度**：实际要完成的任务
- **社会维度**：他人如何看待用户
- **情感维度**：用户如何看待自己

### 5T 原则

每个 JTBD 陈述必须通过 5T 验证：

| 原则 | 检查问题 |
|------|----------|
| True 真实 | 这是用户真正的需求吗？ |
| Tacit 隐性 | 这是未被明说但真实存在的需求吗？ |
| Touch 切身 | 这事直接关系到用户本人吗？ |
| Tension 张力 | 存在挫败感、摩擦或渴望吗？ |
| Trigger 触发 | 什么事件激活了这个需求？ |

### Four Forces of Progress

`
进展 = 推力(Push) + 拉力(Pull) - 惯性(Inertia) - 焦虑(Anxiety)
`

| 力量 | 说明 | 来源 |
|------|------|------|
| Push | 对当前方案的不满 | 痛点、局限、不便 |
| Pull | 新方案的吸引力 | 期望结果、更好的体验 |
| Inertia | 惯性阻力 | 习惯、切换成本、学习曲线 |
| Anxiety | 改变焦虑 | 未知风险、恐惧 |

---

## 🔄 完整执行流程

`
Step 1   判断数据类型（Data Quality Agent）
Step 2   数据质量检查
Step 3   用户画像分析（Persona Agent）
Step 4   情景分析（Context Agent）
         ┌─────────────────────────────┐
         │    判断是否存在行为转换？     │
         └──────┬──────────┬──────────┘
             是/Yes     否/No
                │          │
         Switch Agent   JTBD Agent
         (时间线+4F)    (任务分析)
                │          │
                └────┬─────┘
                     │
Step 6   生成 JTBD（JTBD Agent）
Step 7   生成 Job Map（Job Map Agent）
Step 8   提炼 Needs（Need Agent）
Step 9   生成 Desired Outcomes（Outcome Agent）
Step 10  证据验证（Evidence Validation Agent）
Step 11  机会评分（Opportunity Agent）
Step 12  产品需求翻译（Product Translation Agent）
Step 13  概念生成（Concept Agent）
Step 14  验证计划（Validation Agent）
Step 15  路线图（Roadmap Agent）
Step 16  GTM 策略（GTM Agent）
`

---

## 📊 机会评分模型

| 维度 | 权重 | 范围 |
|------|------|------|
| 用户重要性 | 1.5x | 1-10 |
| 不满意度 | 1.3x | 1-10 |
| 发生频率 | 1.2x | 1-10 |
| 市场规模 | 1.0x | 1-10 |
| 商业价值 | 1.0x | 1-10 |
| 战略契合 | 0.8x | 1-10 |
| 技术可行性 | 0.7x | 1-10 |

### 机会分类

| 分类 | 最低分 | 行动建议 |
|------|--------|----------|
| Core Opportunity | 7.0 | 高优先级，强证据支撑，立即投入 |
| Adjacent Opportunity | 5.0 | 中优先级，需要进一步验证 |
| Exploratory Opportunity | 0.0 | 低优先级，研究阶段 |

---

## ✅ 验证体系

1. **Evidence Checker** — 验证每个洞察引用具体证据
2. **JTBD Quality Checker** — 5T 原则质量门禁
3. **Hallucination Checker** — 检测无用户数据支持的 AI 幻觉
4. **Confidence Score** — 基于证据强度、多样性的置信度评分

`ash
python validators/evidence_checker.py insights.json
python validators/jtbd_quality_checker.py jtbd_output.json
`

---

## 📝 输出模板

| # | 报告部分 | 模板文件 |
|---|----------|----------|
| 1 | Executive Summary | insight_report.md |
| 2 | User Understanding | persona_template.md |
| 3 | Context Analysis | context_map.md |
| 4 | Switch Analysis | switch_analysis.md |
| 5 | JTBD Analysis | jtbd_statement.md |
| 6 | Job Map | job_map.md |
| 7-8 | Need Analysis + Outcomes | (结构化输出) |
| 9 | Evidence Appendix | (见 validators) |
| 10 | Opportunity Ranking | opportunity_matrix.md |
| 11 | Product Recommendation | product_definition.md |
| 12 | Validation Plan | validation_plan.md |
| 13 | Roadmap | roadmap.md |
| 14 | GTM Strategy | gtm_strategy.md |

---

## 🔬 应用案例

| 案例 | 数据类型 | 分析重点 |
|------|----------|----------|
| 智能手机 | 12 份用户深度访谈 | JTBD 提炼、Desired Outcome 工程 |
| 无线耳机 | 8 份切换访谈 | Switch 分析、Four Forces |
| B2B SaaS | 15 份企业用户访谈 | 产品需求翻译、PRD 生成 |
| 汽车购买 | 20 份购车决策访谈 | 购买决策分析、机会评分 |

---

## 📄 许可证

MIT License (c) 2026

---

<div align="center">
  <sub>Built with JTBD 2.0 methodology. Not a JTBD analysis prompt — a complete product innovation operating system.</sub>
</div>




---

<div align="center">
  <h1>JTBD Innovation OS 4.0</h1>
  <p><strong>Enterprise AI User Insight &amp; Product Innovation Operating System</strong></p>
  <p>A Multi-Agent product innovation workflow based on Jobs-to-be-Done 2.0 methodology</p>
  <p>
    <img src="https://img.shields.io/badge/version-4.0.0-blue.svg" alt="Version 4.0.0">
    <img src="https://img.shields.io/badge/status-active-brightgreen.svg" alt="Status: Active">
    <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="License: MIT">
  </p>
</div>

---

## Introduction

**JTBD Innovation OS 4.0** is not just a JTBD analysis prompt. It is a complete **Multi-Agent product innovation operating system** that transforms raw user voices into executable business innovation decisions.

> People do not buy products. They hire products to make progress.

The system covers the full closed loop from user data collection to GTM strategy, with 17 specialized Agents, 14 JTBD methodology frameworks, 4 validator scripts, and 12 output templates.

---

## Target Audience

| Role | Use Case |
|------|----------|
| Product Manager | User research -> Requirements -> PRD -> Roadmap |
| UX Researcher | Interview data -> User insights -> JTBD -> Validation report |
| Innovation Team | Opportunity ID -> Concept generation -> Validation -> GTM |
| Founder | User need discovery -> Product definition -> MVP planning |
| Growth Team | User behavior analysis -> Switch driver ID -> Improvement prioritization |

---

## Architecture

The system is organized in 9 layers, progressively deriving business execution from raw data:

`
User Data
   ↓
Layer 0  Data Understanding     -> Data quality, says-vs-does observation
   ↓
Layer 1  User Understanding     -> Persona profiles, context maps
   ↓
Layer 2  Behavior Analysis      -> Switch analysis, Four Forces
   ↓
Layer 3  Job Discovery          -> JTBD extraction, Job Hierarchy, Job Map
   ↓
Layer 4  Need Definition        -> Need classification, Desired Outcomes
   ↓
Layer 5  Validation             -> Evidence validation, 5T check
   ↓
Layer 6  Innovation Decision    -> Opportunity scoring & prioritization
   ↓
Layer 7  Product Innovation     -> HMW concept generation, Validation plans
   ↓
Layer 8  Business Execution     -> Product roadmap, GTM strategy
`

### Agent Overview

| Layer | Agent | Core Output |
|-------|-------|-------------|
| 0 | Data Quality Agent | Data quality report |
| 0 | Observation Agent | Says-vs-does gap analysis |
| 1 | Persona Agent | Persona profile |
| 1 | Context Agent | Context map |
| 2 | Switch Agent | Switch analysis (timeline + Four Forces) |
| 3 | JTBD Agent | JTBD statement |
| 3 | Job Map Agent | 8-step job process map |
| 4 | Need Agent | Need classification (Pain/Benefit) |
| 4 | Outcome Agent | Desired Outcome statement |
| 5 | Evidence Validation Agent | Validation report + 5T check |
| 6 | Opportunity Agent | Opportunity scoring & ranking |
| 7 | Product Translation Agent | Requirement -> Feature -> User Story |
| 7 | Concept Agent | Concept card (HMW) |
| 7 | Validation Agent | User validation plan |
| 8 | Roadmap Agent | 3-horizon product roadmap |
| 8 | GTM Agent | Go-to-market strategy |

---

## Quick Start

### Installation

Clone to your Codex Skills directory for auto-discovery:

`ash
git clone https://github.com/your-org/jtbd-innovation-os.git ~/.codex/skills/jtbd-innovation-os
`

### Basic Usage

Provide user research data (interview transcripts, surveys, CSV, Excel, PDF, TXT) to Codex. The skill automatically triggers and executes the full analysis pipeline.

**Supported Input Formats:**

| Format | Description | Example |
|--------|-------------|---------|
| Interview transcript | Raw interview text, CN/EN | User interview verbatim |
| CSV | Structured user data | Survey results |
| Excel (.xlsx/.xls) | Tabular data | Feedback summary |
| PDF | Document format | Research report |
| TXT | Plain text | User comments, feedback |

**Supported Languages:** Chinese, English, mixed CN/EN

---

## Project Structure

`
jtbd-innovation-os/
├── SKILL.md                        # Entry point: metadata & workflow
├── README.md                       # This file
├── config/                         # Configuration files
│   ├── workflow_config.yaml        # Workflow orchestration & branching
│   ├── scoring_config.yaml         # 7-dimension scoring parameters
│   └── output_schema.yaml          # Structured output definitions
├── agents/                         # 17 agent modules
│   ├── data_quality_agent/         # Data quality assessment
│   ├── observation_agent/          # User says-vs-does observation
│   ├── persona_agent/              # Persona profiling
│   ├── context_agent/              # Context analysis
│   ├── switch_agent/               # Switch behavior analysis
│   ├── jtbd_agent/                 # JTBD extraction
│   ├── job_map_agent/              # Job process mapping
│   ├── need_agent/                 # Need classification
│   ├── outcome_agent/              # Desired Outcome engineering
│   ├── evidence_validation_agent/  # Evidence validation
│   ├── opportunity_agent/          # Opportunity scoring engine
│   ├── product_translation_agent/  # Product translation
│   ├── concept_agent/              # Concept generation
│   ├── validation_agent/           # Validation planning
│   ├── roadmap_agent/              # Roadmap planning
│   └── gtm_agent/                  # GTM strategy
├── frameworks/                     # 14 JTBD methodology references
├── validators/                     # Python validation scripts
├── templates/                      # 12 structured output templates
└── examples/                       # 4 complete case studies
`

---

## JTBD Core Principles

### What is a Job?

A **Job** is the progress a person wants to make in a particular situation. It has three dimensions:

- **Functional**: The practical task to accomplish
- **Social**: How others perceive the person
- **Emotional**: How the person feels about themselves

### The 5T Principles

Every JTBD statement must pass the 5T check:

| Principle | Question |
|-----------|----------|
| **True** | Does this reflect a genuine user need? |
| **Tacit** | Is this unspoken but real? |
| **Touch** | Does it personally affect the user? |
| **Tension** | Is there frustration or desire? |
| **Trigger** | What event activates this? |

### Four Forces of Progress

`
Progress = Push + Pull - Inertia - Anxiety
`

| Force | Description | Source |
|-------|-------------|--------|
| Push | Dissatisfaction with current solution | Pain points, limitations |
| Pull | Attraction of new solution | Desired outcomes, better experience |
| Inertia | Resistance to change | Habits, switching costs, learning curve |
| Anxiety | Fear of change | Unknown risks, fear of mistakes |

---

## Full Execution Pipeline

`
Step 1   Data type detection (Data Quality Agent)
Step 2   Data quality check
Step 3   Persona analysis (Persona Agent)
Step 4   Context analysis (Context Agent)
         ┌───────────────────────────────┐
         │  Switch behavior detected?     │
         └──────┬────────────┬───────────┘
              Yes             No
                │              │
         Switch Agent      JTBD Agent
         (Timeline+4F)   (Task analysis)
                │              │
                └──────┬───────┘
                       │
Step 6   Generate JTBD (JTBD Agent)
Step 7   Generate Job Map (Job Map Agent)
Step 8   Extract Needs (Need Agent)
Step 9   Generate Desired Outcomes (Outcome Agent)
Step 10  Evidence Validation (Evidence Validation Agent)
Step 11  Opportunity Scoring (Opportunity Agent)
Step 12  Product Translation (Product Translation Agent)
Step 13  Concept Generation (Concept Agent)
Step 14  Validation Planning (Validation Agent)
Step 15  Roadmap (Roadmap Agent)
Step 16  GTM Strategy (GTM Agent)
`

---

## Opportunity Scoring Model

| Dimension | Weight | Range |
|-----------|--------|-------|
| User Importance | 1.5x | 1-10 |
| Dissatisfaction | 1.3x | 1-10 |
| Frequency | 1.2x | 1-10 |
| Market Size | 1.0x | 1-10 |
| Business Value | 1.0x | 1-10 |
| Strategic Fit | 0.8x | 1-10 |
| Technical Feasibility | 0.7x | 1-10 |

### Opportunity Categories

| Category | Min Score | Action |
|----------|-----------|--------|
| Core Opportunity | 7.0 | High priority, strong evidence, invest now |
| Adjacent Opportunity | 5.0 | Medium priority, needs validation |
| Exploratory Opportunity | 0.0 | Low priority, research phase |

---

## Validation System

1. **Evidence Checker** — Validates every insight cites specific evidence
2. **JTBD Quality Checker** — 5T principle quality gate
3. **Hallucination Checker** — Detects AI-generated insights without user data
4. **Confidence Score** — Evidence-based confidence assessment

`ash
python validators/evidence_checker.py insights.json
python validators/jtbd_quality_checker.py jtbd_output.json
`

---

## Case Studies

| Case | Data Type | Focus |
|------|-----------|-------|
| Smartphone | 12 in-depth interviews | JTBD extraction, Desired Outcomes |
| Wireless Headphones | 8 switch interviews | Switch analysis, Four Forces |
| B2B SaaS | 15 enterprise interviews | Product translation, PRD generation |
| Automotive | 20 purchase decision interviews | Decision analysis, Opportunity scoring |

---

## License

MIT License (c) 2026

---

<div align="center">
  <sub>Built with JTBD 2.0 methodology. Not a JTBD analysis prompt — a complete product innovation operating system.</sub>
</div>
