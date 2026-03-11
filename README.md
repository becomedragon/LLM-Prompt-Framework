# LLM Prompt Framework

**中文** | [English](#english)

---

## 中文

### 项目简介

**LLM Prompt Framework** 是一个精心策划的高级 LLM 提示词框架集合，专为复杂推理、多角色模拟和深度思考任务而设计。

每个框架都是经过打磨的结构化提示词，能够引导大语言模型（Claude、GPT-4 等）进行有深度的、有结构的思想探索。

### 愿景

- 📦 收录并改进高质量的结构化 Prompt 框架
- 🧠 为各类 LLM 驱动的深度思考场景提供开箱即用的工具
- 🌍 建立中英双语的提示词社区，降低使用门槛
- 🔧 保持可扩展性，让社区持续贡献新的框架

### 目录结构

```
LLM-Prompt-Framework/
├── README.md                          # 本文件
└── prompts/
    ├── roundtable-seminar/            # 圆桌研讨会框架
    │   ├── README.md                  # 框架说明文档
    │   └── roundtable-seminar-v2.md   # 改进版双语 Prompt
    └── business-structure/            # 商业结构分析框架
        ├── README.md                  # 框架说明文档
        └── business-structure-v2.md   # 改进版双语 Prompt
```

所有提示词框架均位于 `prompts/` 目录下，每个框架拥有独立的子目录。

### 可用框架

| 框架名称 | 目录 | 简介 |
|---|---|---|
| 圆桌研讨会 (Roundtable Seminar) | [`prompts/roundtable-seminar/`](prompts/roundtable-seminar/) | 多角色结构化辩论框架，由主持人引导，邀请代表不同思想的历史/哲学人物进行深度对话 |
| 商业结构分析 (Business Structure Analysis) | [`prompts/business-structure/`](prompts/business-structure/) | 系统战略分析框架，运用涡旋/结构动力学物理隐喻，对公司进行全生命周期结构演变解构 |

### 如何使用

1. 进入感兴趣的框架目录，阅读其 `README.md` 了解用法
2. 打开对应的 `.md` Prompt 文件，复制其中的 Prompt 内容
3. 将内容粘贴到你偏好的 LLM（如 Claude、GPT-4 等）的对话框中
4. 按照框架的使用说明开始交互

> 推荐使用 Claude 3.5+ 或 GPT-4+ 以获得最佳效果。

### 如何贡献

欢迎提交新的提示词框架！步骤如下：

1. 在 `prompts/` 目录下创建新的子目录（使用英文连字符命名，如 `my-new-prompt/`）
2. 在子目录中添加：
   - Prompt 文件（`.md` 格式，建议使用版本号，如 `my-new-prompt-v1.md`）
   - `README.md` 说明文档（包含简介、用法、作者信息等）
3. 更新本文件的"可用框架"表格
4. 提交 Pull Request

### 许可证

本项目采用 [MIT License](LICENSE) 开源协议。所有收录的 Prompt 框架均注明原作者信息，如有侵权请联系删除。

---

## English

### About

**LLM Prompt Framework** is a curated collection of advanced, structured LLM prompt frameworks designed for complex reasoning, multi-role simulation, and deep thinking tasks.

Each framework is a carefully crafted structured prompt that guides large language models (Claude, GPT-4, etc.) through deep, structured intellectual exploration.

### Vision

- 📦 Collect and improve high-quality structured prompt frameworks
- 🧠 Provide ready-to-use tools for LLM-powered deep thinking scenarios
- 🌍 Build a bilingual (Chinese + English) prompt community
- 🔧 Stay extensible so new frameworks can be added over time

### Directory Structure

```
LLM-Prompt-Framework/
├── README.md                          # This file
└── prompts/
    ├── roundtable-seminar/            # Roundtable Seminar framework
    │   ├── README.md                  # Framework documentation
    │   └── roundtable-seminar-v2.md   # Improved bilingual prompt
    └── business-structure/            # Business Structure Analysis framework
        ├── README.md                  # Framework documentation
        └── business-structure-v2.md   # Improved bilingual prompt
```

All prompt frameworks live under `prompts/`, each in its own subdirectory.

### Available Prompts

| Framework | Directory | Description |
|---|---|---|
| Roundtable Seminar (圆桌研讨会) | [`prompts/roundtable-seminar/`](prompts/roundtable-seminar/) | A structured multi-role debate framework where a moderator invites representative historical/philosophical figures to engage in deep dialogue |
| Business Structure Analysis (商业结构分析) | [`prompts/business-structure/`](prompts/business-structure/) | A systems strategy framework using vortex/structural dynamics physics metaphors to deconstruct a company's full lifecycle structural evolution |

### How to Use

1. Browse to the framework directory you're interested in and read its `README.md`
2. Open the `.md` prompt file and copy the prompt content
3. Paste it into your preferred LLM (Claude, GPT-4, etc.)
4. Follow the framework's usage instructions to begin

> Recommended: Claude 3.5+ or GPT-4+ for best results.

### How to Contribute

Contributions of new prompt frameworks are welcome! Steps:

1. Create a new subdirectory under `prompts/` (use kebab-case, e.g. `my-new-prompt/`)
2. Add inside it:
   - The prompt file (`.md` format, versioned, e.g. `my-new-prompt-v1.md`)
   - A `README.md` with description, usage, and author credits
3. Update the "Available Prompts" table in this file
4. Submit a Pull Request

### License

This project is open-sourced under the [MIT License](LICENSE). All included prompt frameworks credit their original authors.
