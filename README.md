# Reveal.js Skill for Gemini CLI 🚀

这是一个专为 **Gemini CLI** 打造的高级技能（Skill），旨在通过 AI 自动化创建专业、美观且响应式的 **reveal.js** 演示文稿（HTML 幻灯片）。

它不仅仅是一个代码生成器，还内置了专业的设计原则、自动布局脚本、溢出检查工具以及浏览器实时编辑功能，让你无需掌握复杂的 CSS 即可交付高质量的幻灯片。

## ✨ 核心特性

- **零构建步骤**：生成纯 HTML 和 CSS，直接在浏览器中运行，无需 Webpack 或 Vite。
- **智能设计驱动**：内置 18 套经过精心挑选的配色方案（从“经典蓝”到“复古彩虹”），并遵循严格的排版和对比度原则。
- **自动脚手架**：使用 `create-presentation.js` 快速生成复杂的幻灯片结构（支持水平、垂直和分隔符幻灯片）。
- **质量保障**：包含 `check-overflow.js` 脚本，可自动检测文字是否超出幻灯片边界。
- **视觉反馈**：支持通过 `decktape` 生成所有幻灯片的截图预览，方便快速审查。
- **即时编辑**：内置 `edit-html.js` 服务，支持在浏览器中点击文字直接修改并保存。

---

## 🛠️ 安装指南

确保你已经安装了 [Gemini CLI](https://github.com/google/gemini-cli)。

### 1. 克隆并准备环境

```bash
git clone https://github.com/ryanbbrown/reveal-js-skill.git
cd reveal-js-skill
npm install
```

### 2. 在 Gemini CLI 中安装技能

你可以通过以下两种方式之一安装此技能：

**方式 A：全局安装（推荐）**
将此技能安装到你的 Gemini 全局配置中，以便在任何项目中使用：
```bash
gemini skills install skills/revealjs
```

**方式 B：软链接安装（开发推荐）**
如果你打算修改技能代码，建议使用软链接：
```bash
gemini skills link skills/revealjs
```

### 3. 验证安装
在终端运行：
```bash
gemini skills list
```
如果在列表中看到 `revealjs`，说明安装成功。

---

## 🚀 如何使用

在 Gemini CLI 会话中，你可以直接向 AI 下达指令。Gemini 会自动调用此技能。

### 常用指令示例

- **创建新演示文稿**：
  > "帮我制作一个关于‘量子计算入门’的演示文稿。使用‘蓝金（Black & Gold）’配色方案，包含 8 张幻灯片。"

- **指定结构**：
  > "创建一个名为‘季度汇报’的 PPT，结构为：封面、3张正文、1个分隔符、2张深入探讨、结语。"

- **检查并修复**：
  > "检查生成的 `presentation.html` 是否有文字溢出，并尝试修复它们。"

- **生成预览**：
  > "为我的演示文稿生成所有幻灯片的截图以便我检查。"

---

## 📂 项目结构

- `skills/revealjs/SKILL.md`: 技能的核心指令和规则手册。
- `skills/revealjs/scripts/`: 核心辅助脚本。
  - `create-presentation.js`: 快速生成幻灯片 HTML 框架。
  - `check-overflow.js`: 检查内容是否超出显示范围。
  - `edit-html.js`: 启动本地服务器进行可视化编辑。
- `skills/revealjs/references/`: 进阶指南（图表使用、动画等）。
- `examples/`: 演示示例。

---

## 🔧 开发辅助工具

生成演示文稿后，你可以手动使用以下工具：

### 1. 文字实时编辑
如果你想微调文案，无需修改 HTML 代码：
```bash
node skills/revealjs/scripts/edit-html.js ./presentation.html
```
然后在浏览器中点击文字即可修改，点击“Save”保存。

### 2. 溢出检查
确保你的幻灯片在任何屏幕上都显示正常：
```bash
node skills/revealjs/scripts/check-overflow.js ./presentation.html
```

### 3. 导出与截图
将幻灯片转换为 PDF 或生成逐页截图：
```bash
npx decktape reveal presentation.html output.pdf --screenshots
```

---

## 📄 许可证

MIT
