<div align="center">

# Whizard Skills

AI 编程代理技能合集（Codex、Claude Code、OpenCode）

[![English](https://img.shields.io/badge/English-blue?style=for-the-badge)](README.md)
[![中文](https://img.shields.io/badge/中文-red?style=for-the-badge)](README_zh.md)

</div>

---

## 技能列表

### [awesome-design-md](./awesome-design-md/)

利用 [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) 中的 DESIGN.md 文件，为 AI 编程代理生成一致的、符合品牌风格的 UI。

#### 功能说明

每个 DESIGN.md 是一份纯文本文档，AI 代理通过读取它来理解视觉风格、设计令牌和组件模式。此技能帮助你选择、集成和使用这些文件来生成高质量 UI。

#### 特性

- **73+ 品牌设计系统**：Stripe、Apple、Tesla、Spotify、Linear、Vercel 等
- **分类浏览**：AI/LLM、开发者工具、金融科技、电商、汽车、媒体
- **风格浏览**：暗色 UI、极简、大胆、电影感、活泼
- **完整目录索引**：包含 URL 和风格关键词，方便快速查找
- **集成工作流**：将 DESIGN.md 添加到项目的分步指南

#### 文件结构

| 文件 | 用途 |
|------|------|
| `SKILL.md` | 主指令、品牌选择指南、工作流 |
| `references/collection-catalog.md` | 73 个品牌的完整目录及 URL |

#### 使用示例

```
# 构建匹配特定品牌的落地页
Use $awesome-design-md to help me build a landing page like Stripe

# 生成带有品牌风格的 UI 组件
Use $awesome-design-md to create a pricing page using the DESIGN.md design system

# 浏览可用的设计系统
Use $awesome-design-md to show me all available dark UI design systems
```

---

### [humanizer](./humanizer/)

去除 AI 生成文本的痕迹，让内容听起来更自然、更人性化。基于维基百科"AI 写作特征"指南。

#### 功能说明

扫描文本中的 33 种已知 AI 写作模式并进行重写，生成自然流畅的文本。支持声音校准，匹配你的个人写作风格。

#### 特性

- **33 种检测模式**：内容、语言、风格、交流和填充词模式
- **声音校准**：提供写作样本，匹配你的个人风格
- **修改前后示例**：每种模式都有清晰的对比示例
- **两轮重写**：初次重写 + 最终审计，确保彻底去除 AI 痕迹

#### 文件结构

| 文件 | 用途 |
|------|------|
| `SKILL.md` | 主指令、33 种模式、工作流 |
| `references/pattern-examples.md` | 33 种模式的详细示例 |

#### 检测模式分类

| 类别 | 数量 | 示例 |
|------|------|------|
| 内容模式 | 6 | 夸大重要性、空洞归因、公式化挑战 |
| 语言模式 | 7 | AI 词汇、系动词回避、被动语态、三段式 |
| 风格模式 | 12 | 破折号滥用、过度加粗、表情符号、标题大写 |
| 交流模式 | 3 | 聊天机器人套话、谄媚语气、免责声明 |
| 填充词 | 5 | 冗余短语、过度模糊化、泛泛总结 |

#### 使用示例

```
# 基础去 AI 化
Use $humanizer to rewrite this AI-generated text to sound more natural

# 声音校准
Use $humanizer to match my writing style from this sample: [sample]

# 清理 ChatGPT 输出
Use $humanizer to remove AI patterns from this article: [text]
```

---

### [ponytail](./ponytail/)

让 AI 代理写更少的代码，强制执行 YAGNI 原则。基于 [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail)（60k+ stars）。

#### 功能说明

向 AI 代理注入"少写代码"规则。在写代码前，代理必须问：这东西需要存在吗？代码库里已经有了？标准库能搞定？一行能搞定？结果：代码量减少 ~54%，成本降低 ~20%，速度提升 ~27%。

#### 特性

- **YAGNI 强制执行**：强制代理在写代码前检查是否已存在
- **最小化解决方案**：能一行就一行，能用标准库就用标准库
- **16+ 代理支持**：Claude Code、Codex、Cursor、Windsurf、Cline、GitHub Copilot 等
- **内置命令**：`/ponytail`（强度）、`/ponytail-review`（审计）、`/ponytail-gain`（记分板）

#### 文件结构

| 文件 | 用途 |
|------|------|
| `SKILL.md` | 主指令、YAGNI 规则、安装指南 |

#### 使用示例

```
# 减少代码膨胀
Use $ponytail to write minimal code for this feature

# 审查过度工程
Use $ponytail-review to audit this diff

# 查看效果
Use $ponytail-gain to see code/cost/speed savings
```

---

### [rtk](./rtk/)

CLI 代理工具，可将常见开发命令的 LLM token 消耗降低 60-90%。基于 [rtk-ai/rtk](https://github.com/rtk-ai/rtk)（66k+ stars）。

#### 功能说明

在 AI 编程工具执行命令前，自动将 Bash 命令重写为更紧凑的等效命令。单个 Rust 二进制文件，零依赖，<10ms 开销。常见命令（如 `git status`、`ls`、`cat`）可节省约 80% token。

#### 特性

- **60-90% Token 节省**：git、cargo、docker、AWS 等命令的紧凑输出
- **14+ AI 工具支持**：Claude Code、Codex、Cursor、Gemini CLI、GitHub Copilot 等
- **四大优化策略**：智能过滤、分组、截断、去重
- **元命令**：`rtk gain`（统计）、`rtk discover`（发现未优化命令）、`rtk session`（最近会话）

#### 文件结构

| 文件 | 用途 |
|------|------|
| `SKILL.md` | 主指令、安装指南、支持的工具 |

#### 使用示例

```
# 减少 AI 会话中的 token 使用
Use $rtk to optimize my command output

# 查看 token 节省统计
Use $rtk gain to see my savings stats

# 发现未优化的命令
Use $rtk discover to find commands not yet optimized
```

---

### [matt-pocock-engineering](./matt-pocock-engineering/)

Matt Pocock 工程技能摘要，用于专业的 AI 辅助开发。基于 [mattpocock/skills](https://github.com/mattpocock/skills)（148k+ stars）。

#### 功能说明

全面介绍技能系统：核心理念（对齐、领域语言、反馈循环、代码设计）、技能分类（Engineering、Productivity、Misc）、调用类型（User-invoked vs Model-invoked），以及关键技能如 `/grill-me`、`/tdd`、`/diagnosing-bugs`、`/improve-codebase-architecture`。

#### 特性

- **四大失败模式**：Agent 不对齐、啰嗦、代码不工作、烂泥球架构
- **17+ 技能覆盖**：Engineering、Productivity、Misc 三大类
- **调用规则**：User-invoked（编排）vs Model-invoked（可复用纪律）
- **核心概念**：编码前对齐、共享领域语言（CONTEXT.md）、TDD、代码设计
- **快速参考**：一目了然的命令速查表

#### 文件结构

| 文件 | 用途 |
|------|------|
| `SKILL.md` | 主指令、技能目录、安装指南 |

#### 使用示例

```
# 学习专业的 AI 工程工作流
Use $matt-pocock-engineering to understand how to apply TDD discipline

# 改进代码库架构
Use $matt-pocock-engineering to explain /improve-codebase-architecture

# 了解对齐工作流
Use $matt-pocock-engineering to show me the alignment workflow
```

---

### [ui-layouts](./ui-layouts/)

使用 [UI-Layouts](https://github.com/ui-layouts/uilayouts) 组件库生成创意动画 React 组件。80+ 生产就绪组件，基于 Tailwind CSS 和 Framer Motion。

#### 功能说明

提供即用型 React 组件目录，用于构建视觉丰富、带动画的网站。组件涵盖视觉特效、动画、表单、弹层、3D 视觉、布局、卡片、媒体画廊、导航和代码展示。

#### 特性

- **80+ 组件**：视觉特效、动画、表单、弹层、3D、布局、卡片、媒体、导航、代码
- **即用型**：自包含组件，无需 CLI 安装器
- **Tailwind + Framer Motion**：现代 React 样式和动画技术栈
- **明暗模式**：通过 CSS 变量内置主题支持
- **完全可定制**：className props、CSS 变量、组件特定选项

#### 文件结构

| 文件 | 用途 |
|------|------|
| `SKILL.md` | 主指令、设置指南、组件模式 |
| `references/components.md` | 80+ 组件的完整分类目录 |

#### 使用示例

```
# 创建动画按钮
Use $ui-layouts to help me create creative animated buttons

# 为页面添加视觉特效
Use $ui-layouts to add sparkle effects and mesh gradients

# 构建轮播组件
Use $ui-layouts to create a smooth image carousel

# 创建滚动动画
Use $ui-layouts to build a sticky scroll section
```

---

## 安装方法

克隆到你的技能目录：

```bash
# Codex / Claude Code
git clone https://github.com/wizenard/whizard_skills.git ~/.codex/skills

# OpenCode
git clone https://github.com/wizenard/whizard_skills.git ~/.config/opencode/skills

# 或者只复制特定技能
git clone https://github.com/wizenard/whizard_skills.git /tmp/whizard_skills
cp -r /tmp/whizard_skills/awesome-design-md ~/.codex/skills/
cp -r /tmp/whizard_skills/humanizer ~/.codex/skills/
cp -r /tmp/whizard_skills/ponytail ~/.codex/skills/
cp -r /tmp/whizard_skills/rtk ~/.codex/skills/
cp -r /tmp/whizard_skills/ui-layouts ~/.codex/skills/
```

## 许可证

MIT
