# 商业结构分析 | Business Structure Analysis

**中文** | [English](#english)

---

## 中文

### 简介

**商业结构分析**是一个系统战略分析框架，让 LLM 扮演一位系统战略分析师，运用物理学隐喻（涡旋/结构动力学）来解构一家公司的商业逻辑和生命周期演变。

框架以「三才结构」（天/人/地）为核心，将公司视为在压力下由向心力与离心力动态平衡形成的「涡漩体」，每个关键历史阶段都对应一个独特的结构形状，并通过 ASCII Art 进行可视化。

### 原作信息

- **原作者**：李继刚
- **原作日期**：2026-01-21
- **剑名**：商业结构
- **剑意**：看懂「公司」的结构形状
- **本版本**：v2（改进版，中英双语）

### 原版 vs 改进版（v2）对比

| 维度 | 原版 | v2 改进版 |
|---|---|---|
| **1. 交互模式** | 单次输出，一次生成全部阶段分析 | 多轮交互指令（`继续/next`、`深入/deeper`、`对比/compare`、`预测/predict`、`止/stop`），每次呈现一个阶段，再等待指令 |
| **2. 知识时效性** | 无时效提示，数据准确性不透明 | 开始时声明训练数据截止日期，每条事实标注置信度（🟢 高/🟡 中/🔴 低），过时信息加 ⚠️ 警告 |
| **3. 竞争对手分析** | 无对比维度 | `对比` 指令触发双涡旋体碰撞分析：边界重叠、结构摩擦带、优势对比、双涡旋 ASCII 图 |
| **4. ASCII 图规范** | 无统一符号约定，输出质量不稳定 | 明确符号规范（`>>>` 离心力、`<<<` 向心力、`vvv` 外部压力、`===` 边界/护城河、`[X]` 核心、`(*)` 摩擦点）并提供模板示例 |

### 用户指令

| 指令 | 作用 |
|---|---|
| `继续` / `next` | 进入下一个历史阶段的分析 |
| `深入` / `deeper` | 对当前阶段进行更深层挖掘 |
| `对比 [公司名]` / `compare [company]` | 引入竞争对手，进行结构碰撞分析 |
| `预测` / `predict` | 基于当前结构轨迹，预测下一个结构相变 |
| `止` / `stop` | 结束分析，生成完整结构演变时间线 |
| `拉取` / `fetch` | 触发数据新鲜度协议，尝试获取最新公开数据 |
| `跳过` / `skip` | 跳过数据获取，以 🔴 低置信度标注相关内容继续分析 |

### 自适应数据新鲜度协议

v2 新增**自适应数据新鲜度协议**，当分析涉及近期数据时自动触发：

- **工具型环境**（Claude Code 等）：自动调用 WebFetch / Bash curl 搜索最新公开信息（最新新闻、季度财报、战略动向、股价等）。
- **非工具型环境**（ChatGPT / Claude Web 等）：优雅降级，输出结构化数据请求清单，引导用户从推荐来源手动获取数据并粘贴。

**触发时机**：分析近 24 个月阶段 | `对比` 指令 | `预测` 指令 | 置信度降至 🟡/🔴

**输出标注**：`📡 实时数据` / `🧠 模型知识` / `📋 用户提供`

### 推荐模型

| 模型 | 适配等级 | 备注 |
|---|---|---|
| Claude 3.5 Sonnet / Claude 3.7 | ⭐⭐⭐⭐⭐ | 最佳，结构化推理能力强，ASCII Art 质量高 |
| GPT-4o / GPT-4 Turbo | ⭐⭐⭐⭐ | 优秀，商业分析深度好 |
| GPT-3.5 / 其他中等模型 | ⭐⭐⭐ | 可用，ASCII Art 质量可能参差 |

### 使用步骤

1. 打开 [`business-structure-v2.md`](business-structure-v2.md)
2. 复制文件中代码块内的全部 Prompt 内容
3. 打开你偏好的 LLM（推荐 Claude 3.5+），新建对话
4. 将 Prompt 粘贴进去，等待系统加载完毕
5. 系统会提示你输入待分析的公司名称
6. 输入公司名称（例如：「拼多多」、「Tesla」、「任天堂」）
7. 系统逐阶段呈现结构分析，使用上方指令表控制进程

---

## English

### About

**Business Structure Analysis** is a systems strategy framework that has the LLM act as a strategic systems analyst, using physics metaphors (vortex / structural dynamics) to deconstruct a company's business logic and lifecycle evolution.

The framework centers on the **"Three-Talent Structure"** (Heaven / Human / Earth), treating a company as a vortex body — dynamically balanced between centripetal and centrifugal forces under pressure. Each pivotal phase in the company's history maps to a unique structural shape, visualized through ASCII Art.

### Original Author

- **Author**: 李继刚 (Li Jigang)
- **Date**: 2026-01-21
- **Original title**: 商业结构 (Business Structure)
- **Sword intent**: Understand the structural shape of a company
- **This version**: v2 (Improved, bilingual)

### Original vs Improved (v2) Comparison

| Dimension | Original | v2 Improvement |
|---|---|---|
| **1. Interaction mode** | Single-shot output — generates all phases at once | Multi-round interactive commands (`继续/next`, `深入/deeper`, `对比/compare`, `预测/predict`, `止/stop`); presents one phase at a time and waits for the next command |
| **2. Knowledge timeliness** | No freshness warnings; data accuracy opaque | States training data cutoff at the start; each factual claim tagged with confidence level (🟢 High / 🟡 Medium / 🔴 Low); outdated information flagged with ⚠️ |
| **3. Competitor analysis** | No comparison dimension | `compare` command triggers dual-vortex collision analysis: boundary overlap, structural friction zone, advantage assessment, dual-vortex ASCII diagram |
| **4. ASCII diagram standards** | No unified symbol convention; output quality inconsistent | Explicit symbol conventions (`>>>` centrifugal, `<<<` centripetal, `vvv` external pressure, `===` boundary/moat, `[X]` core, `(*)` friction point) with a template example |

### User Commands

| Command | Action |
|---|---|
| `继续` / `next` | Proceed to analyze the next historical phase |
| `深入` / `deeper` | Drill deeper into the current phase's structure |
| `对比 [公司名]` / `compare [company]` | Introduce a competitor for structural collision analysis |
| `预测` / `predict` | Based on the current structural trajectory, predict the next phase transition |
| `止` / `stop` | Conclude analysis and generate the full structural evolution timeline |
| `拉取` / `fetch` | Trigger the Data Freshness Protocol to attempt fetching latest public data |
| `跳过` / `skip` | Skip data fetching; mark affected content as 🔴 low confidence and continue |

### Adaptive Data Freshness Protocol

v2 introduces an **Adaptive Data Freshness Protocol** that triggers automatically when recent data is needed:

- **Tool-enabled environments** (Claude Code, etc.): Automatically calls WebFetch / Bash curl to search for the latest public information (news, quarterly earnings, strategic moves, stock price, etc.).
- **No-tool environments** (ChatGPT / Claude Web, etc.): Gracefully degrades to a structured data request checklist, guiding the user to manually retrieve data from suggested sources and paste it in.

**Trigger points**: Analyzing the most recent 24-month phase | `compare` command | `predict` command | Confidence drops to 🟡/🔴

**Output markers**: `📡 Live Data` / `🧠 Model Knowledge` / `📋 User Provided`

### Recommended Models

| Model | Rating | Notes |
|---|---|---|
| Claude 3.5 Sonnet / Claude 3.7 | ⭐⭐⭐⭐⭐ | Best — strong structural reasoning, high-quality ASCII Art |
| GPT-4o / GPT-4 Turbo | ⭐⭐⭐⭐ | Excellent business analysis depth |
| GPT-3.5 / mid-tier models | ⭐⭐⭐ | Usable; ASCII Art quality may vary |

### Usage Steps

1. Open [`business-structure-v2.md`](business-structure-v2.md)
2. Copy the entire prompt content from inside the code block
3. Open your preferred LLM (Claude 3.5+ recommended) in a new chat
4. Paste the prompt and wait for the system to load
5. The system will prompt you to enter the company name to analyze
6. Enter the company name (e.g., "Pinduoduo", "Tesla", "Nintendo")
7. The system presents analysis phase by phase — use the commands above to control the flow
