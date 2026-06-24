<p align="center">
  <img src="https://img.shields.io/badge/ Claude-Code-%23D97706?logo=anthropic&logoColor=white" alt="Claude Code">
  <img src="https://img.shields.io/badge/ Platform-macOS_|_Windows-blue?logo=windows" alt="Platform">
  <img src="https://img.shields.io/badge/ License-MIT-green" alt="License">
  <img src="https://img.shields.io/badge/ Lang-中_｜_EN-brightgreen" alt="Languages">
</p>

<h1 align="center">🚀 Claude Code 新手入门指南</h1>
<h3 align="center"><em>Claude Code Beginner's Guide</em></h3>

<p align="center">
  <strong>从零开始 · 像教小朋友一样有耐心 · 适合大学生的 Claude Code CLI 教程</strong><br>
  <sub>Zero to hero — written with the patience of teaching a child, built for college students</sub>
</p>

---

## 📖 这是什么？

这是一份面向大学生（尤其是"什么都不懂"的新手）的 **Claude Code CLI 使用指南**。不管你之前有没有用过终端、会不会写代码，只要跟着这份指南一步步来，你就能用 Claude Code：

| 🎯 | |
|---|---|
| 📝 | 写课程作业（LaTeX 排版，直接导出 PDF） |
| 🎨 | 做课堂演示（自包含的交互式 HTML，双击即开） |
| 📊 | 画数据图表（Python matplotlib，代码全自动生成） |
| 🔧 | 装各种工具（给个 GitHub 地址，Claude 帮你搞定） |
| 🆘 | 遇到报错直接告诉 Claude，它会帮你修 |

> 💬 **核心哲学**：你只管说清楚要什么，剩下的让 Claude 想办法。不需要你真的会写代码。

---

## 📦 仓库文件一览

| 📄 文件 | 🌐 语言 | 📐 格式 | 💡 说明 |
|---------|---------|---------|---------|
| `claude-code-beginner-guide.md` | 🇨🇳 中文 | Markdown | 用 VS Code / Typora 打开查看 |
| `claude-code-beginner-guide.html` | 🇨🇳 中文 | HTML | 自包含网页，双击浏览器打开 ✨ |
| `claude-code-beginner-guide-en.md` | 🇬🇧 English | Markdown | English Markdown version |
| `claude-code-beginner-guide-en.html` | 🇬🇧 English | HTML | Self-contained webpage ✨ |

---

## 🖥️ 如何下载 HTML 并在浏览器打开？

> HTML 文件是**自包含**的——所有样式、脚本都内嵌在一个文件里，不需要联网，不需要装任何东西。双击就能看！

### 🟢 方法一：直接下载（最简单）

```
第 1 步：点击上面文件列表里的 .html 文件
        （比如 claude-code-beginner-guide.html）

第 2 步：在打开的页面右上角，找到 ⬇️「Download raw file」按钮
        （或者直接右键 → "另存为..."）

第 3 步：保存到你电脑上的任意位置（比如桌面）

第 4 步：双击下载好的 .html 文件
        → 浏览器自动打开，搞定！🎉
```

### 🟡 方法二：下载整个仓库（ZIP）

```
第 1 步：点击仓库主页右上角的绿色「<> Code」按钮

第 2 步：选择「Download ZIP」

第 3 步：解压下载的 .zip 文件

第 4 步：进入解压后的文件夹，双击任意 .html 文件
        → 浏览器打开，搞定！🎉
```

### 🔵 方法三：用 git clone（如果你会的话）

```bash
git clone https://github.com/huiihao/claude-code-beginner-guide.git
cd claude-code-beginner-guide
open claude-code-beginner-guide.html      # Mac
# 或者 start claude-code-beginner-guide.html  # Windows
```

---

## 🧭 指南目录

| # | 📚 章节 | 🗒️ 你会学到 |
|---|---------|------------|
| 1 | 🖥️ 认识 Terminal | `ls` / `cd` / `mkdir` / `cp` / `mv` / `rm` 六条基础命令 |
| 2 | 🚀 启动 Claude Code | 安装、登录、退出、`/resume` 恢复对话、常用指令、快捷键、ESC 后悔药 |
| 3 | 📂 让 AI 读你的文件 | 空格 + `@` 选择文件，一次可以选多个 |
| 4 | 🔮 核心技巧 | 让 Claude 搜索/安装工具、装 GitHub 仓库、装 Skills |
| 5 | 📝 Markdown 文件 | `.md` 是什么？VS Code / 空格键 / Typora 怎么查看 |
| 6 | 📄 LaTeX 文档 | Claude 写 `.tex` → texpage.com 在线编译 → 下载 PDF |
| 7 | 🌐 HTML 演示 | "输出单个 HTML 文件，内嵌所有 CSS 和 JS，无外部依赖" |
| 8 | 📊 Python 绘图 | matplotlib 画折线图/柱状图/饼图/散点图... |
| 9 | 🤔 Plan Mode | 为什么 Claude 老让你做选择？Accept / Reject / Modify 怎么选？ |
| 10 | 🧰 总结 & 模板 | 5 种场景的提示词模板，直接复制改改就能用 |

---

## 🌟 HTML 版特色功能

| ✨ | |
|---|---|
| 🌙 | **深色 / 浅色模式** — 自动跟随系统，手动切换会记住偏好 |
| 📖 | **侧栏目录导航** — 点击跳转，当前位置高亮 |
| 📊 | **阅读进度条** — 页面顶部橙色细线，看到哪一目了然 |
| 📋 | **代码一键复制** — 鼠标悬停代码块，右上角出现复制按钮 |
| ⬆️ | **一键回顶** — 右下角浮动按钮，随时回到开头 |
| ⌨️ | **键盘快捷键** — `Cmd+Shift+T` 切换主题，`T` 回顶部 |
| 📱 | **移动端适配** — 手机/平板也能舒服地看 |

---

## 🏗️ 贡献 & 许可

欢迎提 Issue 和 PR 来改进这份指南！无论是修错别字、补充内容、还是翻译成其他语言，都非常欢迎 🙏

```
MIT License — 随便用，随便改，随便分享
```

---

<p align="center">
  <sub>Made with ❤️ + Claude Code · June 2026</sub>
</p>
