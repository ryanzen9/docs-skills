# docs-skills

文档 Agent Skills 集合，目前包含三个技能：

- `writing-docs` — 技术文档内容润色
- `formatting-docs` — Markdown 格式化规则
- `drawing-docs` — 文档图表绘制指南

## 快速安装

```bash
npx skills add ryanzen9/docs-skills
```

执行后按交互提示选择要安装的 skill 和目标 agent 即可。

> `npx skills add` 是 [skills-cli](https://github.com/antfu/skills-cli) 提供的命令行工具（npm 包名 `skills`），它会自动将 SKILL.md 部署到对应 agent 的技能目录。

---

## Skills 概览

| Skill | 用途 |
| --- | --- |
| `writing-docs` | 撰写、润色、补充技术文档内容 |
| `formatting-docs` | 检查、格式化、美化 Markdown 博文（不改内容） |
| `drawing-docs` | 为文档添加 Mermaid 流程图、架构图、时序图等 |

---

## 安装选项

### 基本用法

```bash
# 安装全部 3 个 skill（默认交互选择）
npx skills add ryanzen9/docs-skills

# 只安装指定的 skill
npx skills add ryanzen9/docs-skills --skill writing-docs --skill formatting-docs

# 先看看有哪些 skill 可用
npx skills add ryanzen9/docs-skills --list

# 非交互模式，全部安装
npx skills add ryanzen9/docs-skills --all
```

## 安装后验证

安装完成后，在 Claude Code 或 Codex 中可直接用 slash command 调用：

```text
/writing-docs
/formatting-docs
/drawing-docs
```

或者用自然语言触发（如 "帮我校验这篇博文的格式"），agent 会根据 skill 的 `description` 自动匹配。

---

## Skill 详解

### writing-docs — 技术文档写作

指导原则：相关性、一致性、简洁性、准确性、吸引力、可读性、完整性。适用于 API 文档、用户手册、技术文章等。

### formatting-docs — Markdown 格式化

8 条格式化规则，按序执行：

1. YAML Front Matter 生成与校验
2. 标题层级规范（h1 保留给 front matter，最深 h3）
3. CJK-Latin 间距（Pangu）
4. 段落与空行
5. 列表标记统一与嵌套深度
6. 代码块语言标识
7. 链接与图片修复
8. 粗体/斜体/分隔线/文件结尾

只改格式，不改内容。

### drawing-docs — 文档图表绘制

首选 Mermaid 文本图，备选 Excalidraw 导出 SVG/PNG。涵盖流程图、时序图、状态图、类图、ER 图、甘特图等。强调可移植性（GitHub + Obsidian 兼容）。

---

## 添加新的 Skill

1. 创建新目录 `your-skill/`
2. 在其中创建 `SKILL.md`，包含 frontmatter：

```yaml
---
name: your-skill
description: 一句话描述 skill 的用途和触发场景
---
```

3. 编写 skill 指令内容
4. 提交 PR

## 参考

- [skills-cli](https://github.com/antfu/skills-cli) — `npx skills add` 的源码仓库
- [agentskills.io](https://agentskills.io) — Agent Skills 开放标准
- [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) — Vercel 官方 skills 合集

## 许可

[MIT](LICENSE)
