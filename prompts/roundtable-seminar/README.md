# 圆桌研讨会 | Roundtable Seminar

**中文** | [English](#english)

---

## 中文

### 简介

**圆桌研讨会**是一个结构化对话框架，模拟一场由理性主持人主导的圆桌讨论。主持人根据用户提出的议题，动态邀请代表不同思想的历史/哲学/文化典型人物，进行一场高强度的、以「求真」为目标的深度辩论。

每轮讨论后，主持人会生成 ASCII 可视化思考框架图，提炼核心矛盾，并推进下一层追问，最终构建出结构化的知识网络。

### 原作信息

- **原作者**：李继刚
- **原作日期**：2025-11-12
- **剑名**：圆桌讨论
- **本版本**：v2（改进版，中英双语）

### 原版 vs 改进版（v2）对比

| 维度 | 原版 | v2 改进版 |
|---|---|---|
| **1. 模型适配性** | 无降级策略，弱模型容易角色混乱 | 新增 `def-config`：`max-participants`（默认 4，范围 2-6）+ `model-capability-level`（high/medium/low），低能力模型自动降至 2-3 人，简化角色定义 |
| **2. 执行规则明确性** | 仅靠 Lisp 伪代码暗示模型行为 | 新增 `def-execution-rules`：明确自然语言指令，强制规定角色声音唯一性、禁止轻易认同、要求逐条回应、主持人追踪共识/分歧、立场变化需显式说明 |
| **3. 角色知识锚定** | 角色仅有 `name`、`stance`、`mbti` | 新增 `core-works`（核心著作列表）、`core-claims`（核心主张）、`speaking-constraint`（发言须基于真实思想体系，禁止捏造立场） |
| **4. 上下文压缩与记忆** | 无跨轮记忆机制，长对话易重复 | `synthesize` 新增生成 `cumulative-consensus`（累积共识）、`unresolved-divergences`（未解分歧）、`discussion-trajectory`（讨论轨迹），每轮强制注入为上下文 |

### 用户指令

| 指令 | 作用 |
|---|---|
| `可` | 接受主持人提出的下一个引导问题，继续推进讨论 |
| `止` | 结束讨论，生成最终知识网络 |
| `深入此节` | 暂停推进，对当前核心争议点进行更深层挖掘 |
| `引入新人物` | 邀请新的代表人物加入圆桌（主持人会提示你输入人物姓名） |
| `拉取` / `fetch` | 触发数据新鲜度协议，尝试获取最新公开数据 |
| `跳过` / `skip` | 跳过数据获取，以 🔴 低置信度标注相关内容继续讨论 |

### 自适应数据新鲜度协议

v2 新增**自适应数据新鲜度协议**，当讨论议题涉及近期事件或数据时自动触发：

- **工具型环境**（Claude Code 等）：自动调用 WebFetch / Bash curl 搜索最新公开信息（新闻、研究论文、政策文件、统计数据等）。
- **非工具型环境**（ChatGPT / Claude Web 等）：优雅降级，输出结构化数据请求清单，引导用户从推荐来源手动获取数据并粘贴。

**触发时机**：议题涉及近 24 个月内的事件 | 代表人物引用近期数据置信度偏低（🟡/🔴）| 主持人检测到可能源于数据过时的事实性分歧

**输出标注**：`📡 实时数据` / `🧠 模型知识` / `📋 用户提供`

### 推荐模型

| 模型 | 适配等级 | 备注 |
|---|---|---|
| Claude 3.5 Sonnet / Claude 3.7 | ⭐⭐⭐⭐⭐ | 最佳，角色扮演能力强，长上下文稳定 |
| GPT-4o / GPT-4 Turbo | ⭐⭐⭐⭐ | 优秀，建议设置 `model-capability-level` 为 `high` |
| GPT-3.5 / 其他中等模型 | ⭐⭐⭐ | 建议设置 `model-capability-level` 为 `medium`，减少参与者 |
| 弱模型 | ⭐⭐ | 建议设置 `model-capability-level` 为 `low`，仅保留 2 人 |

### 使用步骤

1. 打开 [`roundtable-seminar-v2.md`](roundtable-seminar-v2.md)
2. 复制文件中代码块内的全部 Prompt 内容
3. 打开你偏好的 LLM（推荐 Claude 3.5+），新建对话
4. 将 Prompt 粘贴进去，等待系统加载完毕
5. 系统会以主持人身份输出欢迎语，提示你输入议题
6. 输入你感兴趣的话题（例如：「人工智能是否拥有真正的创造力？」）
7. 使用上方指令表控制讨论进程

---

## English

### About

**Roundtable Seminar** is a structured dialogue framework that simulates a moderated roundtable discussion. A rational, meta-cognitive moderator dynamically invites representative historical, philosophical, or cultural figures to engage in high-intensity debate on a user-supplied topic, with the goal of **truth-seeking**.

After each round, the moderator generates an ASCII visualization of the thinking framework, distills core contradictions, and formulates the next layer of inquiry — ultimately producing a structured knowledge network.

### Original Author

- **Author**: 李继刚 (Li Jigang)
- **Date**: 2025-11-12
- **Original title**: 圆桌讨论 (Roundtable Discussion)
- **This version**: v2 (Improved, bilingual)

### Original vs Improved (v2) Comparison

| Dimension | Original | v2 Improvement |
|---|---|---|
| **1. Model adaptability** | No degradation strategy; weaker models easily lose role consistency | Added `def-config`: `max-participants` (default 4, range 2–6) + `model-capability-level` (high/medium/low); low-capability models auto-reduce to 2–3 participants with simpler role definitions |
| **2. Execution rule clarity** | Behavior implied solely by Lisp pseudocode structure | Added `def-execution-rules`: explicit natural language directives enforcing unique character voices, banning easy agreement, requiring direct engagement, tracking consensus/divergence, and explicit acknowledgment of position changes |
| **3. Role knowledge anchoring** | Roles only had `name`, `stance`, `mbti` | Added `core-works` (key works/theories list), `core-claims` (fundamental intellectual positions), `speaking-constraint` (arguments must be grounded in the person's actual documented thought system) |
| **4. Context compression & memory** | No cross-round memory; long conversations tend to repeat | `synthesize` now generates `cumulative-consensus`, `unresolved-divergences`, and `discussion-trajectory`; these are injected as mandatory context at the start of each new round |

### User Commands

| Command | Action |
|---|---|
| `可` (Continue) | Accept the moderator's next guiding question and advance the discussion |
| `止` (Stop) | End the discussion and generate the final knowledge network |
| `深入此节` (Deepen) | Pause advancement and dig deeper into the current core contradiction |
| `引入新人物` (Add figure) | Invite a new representative figure to join the roundtable |
| `拉取` / `fetch` | Trigger the Data Freshness Protocol to attempt fetching latest public data |
| `跳过` / `skip` | Skip data fetching; mark affected content as 🔴 low confidence and continue |

### Adaptive Data Freshness Protocol

v2 introduces an **Adaptive Data Freshness Protocol** that triggers automatically when the topic involves recent events or data:

- **Tool-enabled environments** (Claude Code, etc.): Automatically calls WebFetch / Bash curl to search for the latest public information (news, research papers, policy documents, statistical data, etc.).
- **No-tool environments** (ChatGPT / Claude Web, etc.): Gracefully degrades to a structured data request checklist, guiding the user to manually retrieve data from suggested sources and paste it in.

**Trigger points**: Topic involves events within the last 24 months | A representative cites recent data with low confidence (🟡/🔴) | Moderator detects factual disagreements that may stem from outdated information

**Output markers**: `📡 Live Data` / `🧠 Model Knowledge` / `📋 User Provided`

### Recommended Models

| Model | Rating | Notes |
|---|---|---|
| Claude 3.5 Sonnet / Claude 3.7 | ⭐⭐⭐⭐⭐ | Best — strong role-play, stable long context |
| GPT-4o / GPT-4 Turbo | ⭐⭐⭐⭐ | Excellent — set `model-capability-level` to `high` |
| GPT-3.5 / mid-tier models | ⭐⭐⭐ | Set `model-capability-level` to `medium`, fewer participants |
| Weaker models | ⭐⭐ | Set `model-capability-level` to `low`, 2 participants only |

### Usage Steps

1. Open [`roundtable-seminar-v2.md`](roundtable-seminar-v2.md)
2. Copy the entire prompt content from inside the code block
3. Open your preferred LLM (Claude 3.5+ recommended) in a new chat
4. Paste the prompt and wait for the system to load
5. The moderator will greet you and ask for a topic
6. Enter your topic (e.g., "Does AI have genuine creativity?")
7. Use the commands above to control the discussion flow
