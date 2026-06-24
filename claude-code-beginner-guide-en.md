# 🚀 Claude Code Beginner's Guide

> *— Written for college students who "know nothing" (but you're actually pretty smart!)*

---

Hello! If this is your first time hearing about "Claude Code," your first time opening "Terminal," or even your first time typing commands on a computer — this guide is for you. Don't worry. Follow along step by step, and you'll turn Claude Code into your super assistant for homework, projects, and data visualization!

Let's start from the very, very basics 🐣

---

## 📖 Table of Contents

1. [Getting Ready: Meet the Terminal](#1-getting-ready-meet-the-terminal)
2. [Starting Claude Code](#2-starting-claude-code)
3. [Letting AI Read Your Files](#3-letting-ai-read-your-files)
4. [Core Tips for Getting Things Done](#4-core-tips-for-getting-things-done)
5. [About .md Files (Markdown) — What Software to Use?](#5-about-md-files-markdown--what-software-to-use)
6. [Outputting LaTeX Documents (Essential for Coursework)](#6-outputting-latex-documents-essential-for-coursework)
7. [Outputting Interactive HTML Presentations](#7-outputting-interactive-html-presentations)
8. [Drawing Data Charts with Python](#8-drawing-data-charts-with-python)
9. [Why Does Claude Keep Asking Me Questions? — Plan Mode Explained](#9-why-does-claude-keep-asking-me-questions--plan-mode-explained)
10. [Summary & Handy Prompt Templates](#10-summary--handy-prompt-templates)

---

## 1. Getting Ready: Meet the Terminal

### 1.1 What Is the "Terminal"?

The Terminal is a window where you **talk to your computer using text**. Instead of clicking around with your mouse, you just **type a few words** and the computer understands and executes them. Pretty cool, right?

### 1.2 How to Open It

On a Mac, the easiest way:

> 🔍 Press `Command + Space` (Spotlight Search), type **`terminal`**, then press Enter.

Boom! A window with black background and white text (or maybe white background and black text) pops up. Don't be intimidated — it's just waiting for you to speak.

> 💡 **Tip**: If the default font is too small, press `Command + +` to zoom in, `Command + -` to zoom out.

#### 🪟 For Windows Users — How to Open the Terminal

On Windows, there are several ways:

| Method | How | Recommendation |
|--------|-----|---------------|
| **Search** | Press `Win key`, type **`powershell`** or **`terminal`**, press Enter | ⭐⭐⭐ Best |
| **Run dialog** | Press `Win + R`, type **`cmd`**, press Enter | ⭐⭐ Traditional |
| **Right-click Start** | Right-click the Start button → choose "Windows PowerShell" or "Terminal" | ⭐⭐ |

> 🪟 **We recommend PowerShell or Windows Terminal** — don't use the old CMD (Command Prompt). PowerShell supports modern commands that are almost identical to the Mac commands taught in this guide.

> 🪟 **Another great option: Git Bash**. When you install Git for Windows, it comes with a Git Bash terminal that fully supports all Mac/Linux-style commands (`ls`, `cd`, `mkdir`, etc.) with zero additional learning.

### 1.3 The 6 Commands You Must Know

These commands are just like dragging and dropping in the "File Manager," except you use words instead of a mouse. Every command follows this pattern:

```
command [options] [target]
```

Let's meet them one by one:

---

#### 📂 `ls` — See What's Here

```bash
ls
```

**What it does**: Lists all files and subfolders in the current folder.

| Common Variant | Meaning |
|---------------|---------|
| `ls` | List all files in the current directory |
| `ls -l` | Show detailed info (size, date) |
| `ls -a` | Include hidden files (those starting with `.`) |
| `ls -la` | Detailed info + hidden files — most commonly used! |

---

#### 🚪 `cd` — Enter a Folder

```bash
cd folder-name
```

**What it does**: Changes your current folder (like double-clicking into a folder).

| Common Usage | Meaning |
|-------------|---------|
| `cd Desktop` | Go to Desktop |
| `cd ..` | Go up one level |
| `cd ~` | Go back to your "home" directory |
| `cd /` | Go to the very top level (root) |

> 🧠 **Understanding paths**:
> - `~` = `/Users/your-username`, your "home"
> - `.` = current folder
> - `..` = parent folder
> - Think of it like giving directions: "home → leave neighborhood → take subway → arrive." A path is your "address."

---

#### 📁 `mkdir` — Create a New Folder

```bash
mkdir new-folder-name
```

```bash
mkdir Homework
```

After running this, a folder called "Homework" appears in the current directory.

---

#### 📝 `cp` — Copy a File

```bash
cp source-file destination
```

```bash
cp report.txt ~/Desktop/
```

↑ Copies "report.txt" to the Desktop.

| Common Variant | Meaning |
|---------------|---------|
| `cp -r folder destination` | Copy an entire folder (`-r` = recursive) |

---

#### 🚚 `mv` — Move / Rename

```bash
mv source destination
```

**Dual identity**:
- If the destination is another directory → move
- If the destination is a new name → rename

```bash
mv report.txt ~/Documents/    # Move to Documents folder
mv old-name.txt new-name.txt  # Rename
```

---

#### 🗑️ `rm` — Delete a File

```bash
rm filename
```

> ⚠️ **Warning!** Files deleted in the Terminal do not go to the Trash — once deleted, they're gone for real! Double-check before you hit Enter!!

```bash
rm useless-draft.txt          # Delete one file
rm -r entire-folder/          # Delete a folder (be careful!)
rm -rf entire-folder/         # Force delete (BE VERY CAREFUL!!)
```

---

#### 🪟 For Windows Users: Command Cheat Sheet

If you're using **PowerShell** or **Windows Terminal**, all the Mac commands above **work exactly as shown**! `ls`, `cd`, `mkdir`, `cp`, `mv`, `rm` all run fine in PowerShell.

If you're using the old-school **CMD (Command Prompt)**, here's the mapping:

| Function | Mac / PowerShell | CMD (Legacy) | Notes |
|----------|-----------------|-------------|-------|
| List files | `ls` | `dir` | PowerShell supports both |
| Change directory | `cd` | `cd` | Exactly the same ✅ |
| Create folder | `mkdir` | `mkdir` or `md` | Exactly the same ✅ |
| Copy file | `cp` | `copy` | PowerShell supports both |
| Move / Rename | `mv` | `move` | PowerShell supports both |
| Delete file | `rm` | `del` | PowerShell supports both |

> 🪟 **We strongly recommend using PowerShell or Git Bash** — learn one set of commands that works on both Mac and Windows. All subsequent command examples in this guide are based on Mac/PowerShell style.

### ✅ Quick Practice

Open your Terminal and try this drill:

```bash
cd ~/Desktop              # Go to Desktop
mkdir claude-test         # Create a folder called claude-test
cd claude-test            # Enter it
ls                        # See what's inside (should be empty)
cd ..                     # Go back to Desktop
rm -r claude-test         # Delete the test folder
```

If you got through all of that, congratulations — you now know basic Terminal operations! 🎉

### 1.4 Understanding File Paths on Mac (Display Name ≠ Actual Path)

Your Mac's operating system may show folder names in your language in Finder, but in Terminal, **they go by their actual English names**:

| What Finder Shows | Actual Path in Terminal | Full Path |
|-------------------|------------------------|-----------|
| Desktop | `Desktop` | `~/Desktop` or `/Users/your-username/Desktop` |
| Downloads | `Downloads` | `~/Downloads` |
| Documents | `Documents` | `~/Documents` |
| Pictures | `Pictures` | `~/Pictures` |
| Music | `Music` | `~/Music` |
| Movies | `Movies` | `~/Movies` |
| Applications | `Applications` | `/Applications` |

> 🧠 **Remember this rule**: What you see in Finder is a "display name" — the Terminal cares about the "real name" (path name). **Paths always use the English names.**

#### 🪟 Paths on Windows

Windows paths look different from Mac paths, but they're easy to understand:

| Concept | Mac | Windows |
|---------|-----|---------|
| Root | `/` | `C:\` (or D:\, E:\...) |
| Home | `~` = `/Users/your-username` | `C:\Users\your-username` |
| Desktop | `~/Desktop` | `C:\Users\your-username\Desktop` |
| Downloads | `~/Downloads` | `C:\Users\your-username\Downloads` |
| Separator | `/` (forward slash) | `\` (backslash) **or** `/` (forward slash works too) |

> 🪟 **Good news**: In PowerShell and Git Bash, you can keep using `/` as the separator — no need to wrestle with `\`! For example, `cd ~/Desktop` works fine in Windows PowerShell. Claude Code also uses `/` internally for all paths.

#### What does `/` mean in a path?

`/` is a "separator" between folders, just like `/` in a URL:

```
~/Downloads/test
```

In plain English: **"home → Downloads → test (a folder or a file)"**

- `test` could be a **folder** or a **file** — you can't tell from the path alone. Use `ls` to check.
- If it has an extension (like `test.txt`, `test.py`, `test.html`), it's almost certainly a file.

#### Naming Tips

When naming files and folders, try to:
- ❌ Avoid non-English characters (some tools break)
- ❌ Avoid spaces (`my homework.txt` → you'd have to type `my\ homework.txt` or use quotes in Terminal)
- ✅ Use English + underscores/hyphens (e.g., `homework_1.txt`, `course-project`)

### 1.5 Good Habit: One Project, One Folder

Before you start using Claude Code for a course assignment, I strongly recommend this habit:

```bash
# Step 1: Create a dedicated folder for each course/project
mkdir ~/Desktop/digital-signal-processing-hw

# Step 2: cd into it
cd ~/Desktop/digital-signal-processing-hw

# Step 3: Launch Claude from inside this folder
claude
```

**Why do this?** 🎯

- Claude's "field of view" is centered on the folder you launched it from — it more easily sees files in that folder
- You won't mix up files from different courses
- The conversation context (history) is tied to the project — picking up where you left off is much clearer
- Finding files later is easy — no messy desktop full of scattered files

> 💡 **Pro tip**: If you want Claude to see files already in a folder, use the `@` symbol covered in Section 3.

---

## 2. Starting Claude Code

### 2.1 Check If Claude Code Is Already Installed

In Terminal, type:

```bash
claude --version
```

If you see a version number (like `v1.0.x`), it's installed. Skip to 2.3.

If you see `command not found: claude`, follow 2.2 to install it.

### 2.2 Installing Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

> If you get `npm: command not found`, your Mac doesn't have Node.js yet. Don't panic — here's the easiest fix:
>
> 1. Go to [nodejs.org](https://nodejs.org)
> 2. Download the **LTS** version on the left (the one recommended for most users)
> 3. Double-click the `.pkg` file to install, clicking "Continue" all the way through
> 4. After installation, **close Terminal and reopen it**
> 5. Try `npm install -g @anthropic-ai/claude-code` again

### 2.3 Launch!

```bash
claude
```

After you press Enter, **the first time** will open your browser to log in to your Anthropic account. Just follow the prompts (you can use a Google account to sign in).

Once logged in, return to Terminal and you'll see something like this:

```
┌─────────────────────────────────────────────┐
│  Claude Code v1.x.x                         │
│  Type /help for available commands          │
│                                             │
│  >                                           │
└─────────────────────────────────────────────┘
```

The `>` is where you talk to Claude. You can type in plain English! For example:

```
Help me write an outline for my course assignment
```

---

> 💡 **Tip**: When you want to exit Claude Code, type `/exit` or press `Ctrl + C` twice.

### 2.4 How to Exit Claude Code

There are several ways to end a conversation:

| Method | Operation | Effect |
|--------|-----------|--------|
| Graceful exit | Type <code>/exit</code> | Exits cleanly; conversation history is preserved |
| Force quit | Press <code>Ctrl + C</code> **twice** | Equivalent to "I'm done talking, bye" — history is still preserved |
| Single Ctrl+C | Press once | Only interrupts the current operation; does not exit |

> 💡 **Recommendation**: Get used to **double-tapping `Ctrl + C`** to exit — quick and easy. After exiting, you're back at the regular Terminal prompt and can type other commands.

### 2.5 Resuming a Previous Conversation

Chatted halfway yesterday and want to continue today? Use this:

```bash
# First cd to your project folder
cd ~/Desktop/digital-signal-processing-hw

# Then launch Claude
claude

# Inside Claude Code, type:
/resume
```

**`/resume`** will show a list of past conversations — use the arrow keys to pick one, press Enter, and continue chatting!

It's just like chat history in a messaging app — Claude remembers everything you talked about before.

> 💡 **Note**: `/resume` shows conversations you started **inside this folder**. This is another reason the "one project, one folder" habit from 1.5 pays off — conversations from different courses won't get mixed up.

### 2.6 Common Built-in Claude Code Commands

Inside Claude Code's input box, anything starting with `/` is a built-in command. Here are the most useful ones:

| Command | What It Does | When to Use It |
|---------|-------------|----------------|
| `/help` | Show all available commands | When you forget a command |
| `/exit` | Exit Claude Code | Done chatting, heading out |
| `/resume` | View and resume past conversations | Picking up where you left off |
| `/clear` | Clear current conversation context | When the topic has gone off the rails |
| `/cost` | Show token usage for this session | When you want to know how much quota you've used |
| `/status` | View current session status | See what Claude is up to |
| `/add-dir` | Add a folder to Claude's view | Let it see more files |

> 💡 Type `/help` anytime to get the latest list of commands.

### 2.7 Running Into Problems? Just Tell Claude!

This is the single most important principle — **you don't actually need to know how to code; you just need to know how to "tell Claude what happened."**

| Your Situation | What You Say to Claude | What Claude Does |
|---------------|----------------------|-----------------|
| Code threw an error | "This code gave an error: `[paste error]`, please fix it" | Diagnoses and fixes the error |
| Want to install a tool | "I want to use ffmpeg for video processing but I don't have it — please install it" | Searches and installs |
| No idea how to do something | "I want to chart CSV data into graphs. I have zero clue — please walk me through it step by step" | Writes code + explains |
| Code is too slow | "This program runs way too slow. Can you optimize it?" | Analyzes and optimizes |
| Feeling frustrated 😤 | "This stupid code just won't work. I'm about to lose it." | Comforts you + helps debug |

> 🎯 **Remember**: Claude Code isn't just a coding tool — it's like an **all-purpose TA sitting right next to you** — it can install things, fix errors, explain concepts, and even listen to you vent. Just describe the problem clearly. **You don't need to actually know how to code.**

### 2.8 Typed Something Wrong / Hit Enter by Accident? No Worries — ESC Is Your "Undo Button"

When using Claude Code, you might run into these awkward moments:

| Scenario | Your Inner Monologue |
|----------|---------------------|
| Typed a long message, realized it's poorly worded | "Ugh, can I take that back…" |
| Accidentally hit Enter before finishing | "Wait, I wasn't done!!" |
| Claude started answering but you want to change your request | "No no, that's not what I meant!" |
| Don't like this response and want to go back | "This answer is bad. I want to rewind…" |

**The solution is super simple — just press the `ESC` key!**

| Action | Effect |
|--------|--------|
| Press **1 time `ESC`** | 🛑 Interrupt the current conversation / Cut Claude off mid-sentence |
| Press **multiple times `ESC`** | ⏪ Pops up a "rewind to where?" selector — you can step back through conversation checkpoints one by one |

> 🎮 Think of `ESC` as the **"pause + load save" button in a video game**:
> - Press once → pause the current turn
> - Press a few times → brings up a list of save points, pick one to go back

This way, you never have to fear "saying the wrong thing" — you can always undo!

### 2.9 Handy Keyboard Shortcuts for Claude Code

#### Claude Code — Specific Shortcuts

| Shortcut | What It Does | When to Use |
|----------|-------------|-------------|
| `ESC` | Interrupt / rewind conversation | Typed something wrong, unhappy with response, want to go back |
| `Alt + Enter` | New line (without sending) | Writing multi-line content — Enter won't send, just starts a new line |
| `Alt + V` | Paste an image | Paste a screenshot into the conversation for Claude to see (a picture is worth ten thousand words!) |

> 📸 **About pasting images**: If code throws an error, just screenshot it and `Alt+V` — way faster than manually copying error messages. Claude can "see" the content in images.

#### Terminal — General Shortcuts (Also Work Inside Claude Code)

> ⚠️ **Mac and Windows shortcuts differ!** The table below shows **Mac** shortcuts. If you're on Windows, swap `Cmd` for `Ctrl` (except for `Ctrl+U/A/E/W` — those control keys are the same on both platforms).

| Shortcut (Mac) | Shortcut (Windows) | What It Does | When to Use |
|----------------|-------------------|-------------|-------------|
| `Cmd + C` | `Ctrl + C` | Copy selected text | — |
| `Cmd + V` | `Ctrl + V` | Paste text | — |
| `Ctrl + U` | Same | Quickly delete entire line | "I typed a bunch and it's all wrong — nuke it" |
| `Ctrl + A` | Same | Jump to beginning of line | Want to add something at the start |
| `Ctrl + E` | Same | Jump to end of line | Want to keep typing at the end |
| `Ctrl + W` | Same | Delete previous word | Quickly remove the word you just mistyped |
| `Ctrl + K` | Same | Delete from cursor to end of line | Kill the second half of a line |
| `Ctrl + Y` | Same | Paste what you just deleted | "Oops, deleted too much — give it back!" |

> 💡 **Tip**: `Ctrl + U` is a total lifesaver — when you've typed a long command and realize it's all wrong, don't wear out your Backspace key; just `Ctrl + U` and it's gone in one second!

> 🍎 **Important for Mac users**: In Mac Terminal, `Ctrl + C` is **interrupt signal** (NOT copy!) — that's exactly why Section 2.4 says to use `Ctrl + C` twice to exit Claude. For copy/paste, use `Cmd + C` / `Cmd + V`.

---

## 3. Letting AI Read Your Files

Claude is very smart, but it doesn't "automatically see" the files on your computer. You need to **manually tell it** which ones to read.

### 3.1 How to Do It (Super Easy)

1. In Claude Code's input box, first **press the Spacebar once**
2. Then type **`@`** (that's Shift+2)
3. A file list will pop up at the bottom of the screen — use the **up/down arrow keys** to select a file
4. Press **Enter** to confirm

Like this:

```
> Please check this code for any issues
```

(After pressing Space + @, the file picker pops up)

```
> Please check this code for any issues @homework1.cpp
```

### 3.2 You Can Select Multiple Files

After typing `@`, you can repeat the operation to select multiple files for Claude to look at together. For example:

```
> Please analyze the relationship between @src/main.py and @src/utils.py
```

### 3.3 Why Let Claude Read Files First?

Here's an analogy 🌰: You wouldn't tell someone who has never read your thesis, "Help me fix Chapter 3." Same idea — Claude needs to **see your file contents first** before it can give you useful advice.

> 💡 **Remember**: If you forget which folder your file is in, first use `ls` and `cd` in Terminal to browse around, find the target file, note its path and name, then reference it inside Claude Code.

---

## 4. Core Tips for Getting Things Done

### 4.1 The Magic Spell 🔮

Your computer might not have much special software installed — that's totally normal! Claude can **automatically search, install, and invoke** the tools you need. Just add something like this to your prompt:

> **"Please search / invoke / install relevant skills or GitHub repositories to complete this task."**

### 4.2 Example

❌ **Weak prompt**:
```
Draw a data chart for me
```

✅ **Better prompt**:
```
Use Python's matplotlib to draw a data chart for me. If matplotlib isn't installed, please install it first.
If there are relevant skills available, please search for and invoke MCP tools or GitHub repos to help.
```

### 4.3 What Claude Can Do for You

| What You Need | What You Can Say |
|--------------|-----------------|
| Install a Python package | "Please install xxx first, then write the code" |
| Download a GitHub project | "Please clone the xxx repo from GitHub" |
| Invoke a specific tool | "Please install and use pandoc to convert the file to PDF" |
| Search for existing solutions | "Please search for any existing libraries that can handle this task" |

### 4.4 Making Claude Install from a GitHub Repository

Sometimes the tool you want can't just be `pip install`'d — it might be an open-source project on GitHub. Don't worry — Claude can handle that too!

#### Example: Installing claude-hud (an enhanced UI plugin for Claude Code)

```
Please install the tool from https://github.com/jarrodwatts/claude-hud.
Please complete the following steps:
1. Clone this repository locally
2. Install dependencies according to its README
3. Configure it to work with Claude Code
```

Claude will read the repository's README on its own, figure out the installation process, and walk you through it step by step — you don't need to read any docs yourself.

> 🎯 **Universal template**:
> ```
> Please install this GitHub repository: [paste repo URL here]
> If there are additional dependencies, please install them too.
> ```

### 4.5 Making Claude Install Skills

Skills are "plugins" for Claude Code. Once installed, Claude gains the corresponding capabilities.

#### Example: Installing Anthropic's Official Skills Collection

```
Please install the skills from https://github.com/anthropics/skills.
Follow the repository's instructions to configure all available skills in my Claude Code.
```

Once installed, Claude can use these skills to handle more complex tasks.

> 💡 **What are Skills?** Think of them as "specialized training" you install for Claude — without them, Claude knows a little about everything; with a specific skill installed, it becomes much more of an expert in that area.

> 💡 **Core mindset**: Don't assume Claude "can't do it." Just state your needs clearly and let Claude figure out the tools on its own!

---

## 5. About .md Files (Markdown) — What Software to Use?

### 5.1 What Is Markdown?

Markdown (`.md` for short) is a **super simple formatting language**. You don't need to click "Bold" or "Heading" buttons like in Word — just add a few symbols around your text.

This very document you're reading is written in Markdown! Here's a comparison:

| Desired Effect | Markdown Syntax | Final Result |
|---------------|----------------|--------------|
| Main heading | `# This is a heading` | Large, bold heading |
| Subheading | `## This is a subheading` | Slightly smaller heading |
| Bold | `**bold text**` | **bold text** |
| Italic | `*italic*` | *italic* |
| List | `- item one` | • item one |
| Link | `[text](url)` | Clickable hyperlink |
| Inline code | `` `code snippet` `` | `code snippet` |
| Code block | ` ``` code ``` ` | Syntax-highlighted code box |

> 🎯 **Key point**: Claude Code often outputs content in Markdown format! So you need to know how to view it.

### 5.2 What Software to Open .md Files With?

Your Mac has several ways to view Markdown files, ranging from simple to pro:

---

#### 🌟 Option 1 (Recommended): Visual Studio Code (VS Code)

The most popular editor among programmers — **free and powerful**.

1. Go to [code.visualstudio.com](https://code.visualstudio.com) to download and install
2. Open the `.md` file with VS Code
3. Press `Command + Shift + V` → **a live preview window opens on the right** — source code on the left, rendered result on the right

> ✅ **Pros**: Free, powerful, side-by-side preview, and you can edit code too

---

#### 📝 Option 2 (Easiest): Mac's Built-in "Quick Look"

**No software installation required!**

1. Find the `.md` file in Finder
2. **Select the file** → press the **Spacebar**
3. A preview window pops up showing the rendered result

> ✅ **Pros**: Zero installation, fastest
> ⚠️ **Cons**: View-only, can't edit; some complex formatting doesn't display well

---

#### 🖊️ Option 3: Mac's Built-in "TextEdit"

1. Double-click the `.md` file to open it in TextEdit
2. You'll see the Markdown **source code** (with `#`, `*`, etc.)
3. You can edit the text

> ⚠️ TextEdit won't render Markdown — what you see is the "source code." But editing text works fine.

---

#### 🎨 Option 4 (Prettiest): Typora

If you want Markdown to look as nice as a Word document:

1. Go to [typora.io](https://typora.io) to download
2. Open `.md` files with Typora
3. **WYSIWYG** (What You See Is What You Get) — as you type, it shows the formatted result directly, no preview toggle needed

> ✅ **Pros**: Minimalist interface, WYSIWYG, easy PDF/HTML export
> ⚠️ **Cons**: The full version costs ~$15, but the trial version works indefinitely

---

### 5.3 Quick Comparison

| Software | Price | Preview Method | Best For |
|----------|-------|---------------|----------|
| **Quick Look** (Spacebar) | Free | Press Space to preview | Just a quick glance |
| **TextEdit** | Free | No preview | Simple text edits |
| **VS Code** | Free | `Cmd+Shift+V` side preview | 🔥 **Most recommended** |
| **Typora** | Paid | WYSIWYG | Frequent document writers |

### 5.4 What to Do When Claude Outputs Markdown

1. After Claude outputs Markdown content, **copy all of it**
2. Create a new file in VS Code (or another editor)
3. Paste and save as `xxx.md`
4. Press `Command + Shift + V` (VS Code) or Spacebar (Finder) to view the result

> 💡 **Tip**: If you want Claude to convert Markdown directly to HTML, say: **"Please output the above Markdown as a single HTML file with all CSS and JS inline"** — then double-click to open, and you'll see beautiful formatting right in your browser!

---

## 6. Outputting LaTeX Documents (Essential for Coursework)

> Many STEM courses require beautifully typeset assignments. LaTeX was created exactly for this. Don't be scared — you don't need to learn LaTeX syntax. Claude writes it; you just need to compile it.

### 6.1 What Is a `.tex` File?

`.tex` is a LaTeX source file — it contains your **content and formatting instructions**. "Compile" it, and it turns into a beautiful PDF.

### 6.2 Making Claude Write LaTeX

Tell Claude:

```
Please generate a LaTeX document (.tex file) for my course assignment on [topic].
Requirements: support for English (and Chinese if needed via ctex), with title, author, table of contents, sections,
and properly formatted math equations.
```

Claude will output a complete `.tex` file as a code block.

### 6.3 How to Compile → Use texpage.com

Since your computer probably doesn't have a LaTeX compiler (which is several GB), I recommend the online service **[texpage.com](https://texpage.com)**:

#### Compilation Steps:

```
Step 1: Open your browser and go to https://texpage.com
Step 2: Click "New Project" in the top right corner
Step 3: Give your project a name, like "Course Assignment"
Step 4: Copy-paste all of Claude's generated .tex code
Step 5: Click the "Compile" button at the top (Compile / ▶ button)
Step 6: Once compilation succeeds, click "Download PDF"
```

> 📸 The whole process is as simple as copying text into Google Docs and clicking "Export as PDF"!

### 6.4 Complete Prompt Template

```
Please generate a complete LaTeX document (.tex file) with the following requirements:
- Document type: article (with title, author, abstract, sections)
- Content: about [your assignment topic]
- Include at least one math equation
- Include one table
- Clean, well-formatted code with appropriate comments

At the top of the code, add this comment:
% Copy this file's content to https://texpage.com to compile online
```

### ✅ Quick Practice

Use the template above to have Claude generate a LaTeX document, then go to texpage.com, compile it, and see if you can successfully export a PDF!

> 💡 **Tip**: If compilation throws errors, **copy the error message to Claude** and it can fix them. Like this: `@error-log.txt This LaTeX compilation produced these errors. Please fix them.`

---

## 7. Outputting Interactive HTML Presentations

For class presentations, defense talks, data reports… often you need something **beautiful that opens right in a browser**.

### 7.1 The Magic Spell 🎩

Tell Claude this one line — it works like a charm:

> **"Please output a single HTML file with all CSS and JS code inline, with zero external dependencies."**

### 7.2 Why These Requirements?

| Requirement | Reason |
|------------|--------|
| **Single HTML file** | No need to carry around a folder full of files — one file does it all |
| **Inline CSS** | No separate `.css` file needed; styles are written directly inside the HTML |
| **Inline JS** | No separate `.js` file needed; interactive logic is written directly inside the HTML |
| **Zero external dependencies** | No internet connection needed for loading anything — works even offline |

### 7.3 Complete Template

```
Please generate an interactive presentation webpage with these requirements:
- Output a single HTML file with all CSS and JS code inline, zero external dependencies
- Topic: about [your subject]
- Style: modern, clean, suitable for classroom presentation
- Content includes: title slide, 3-4 content slides, summary slide
- Support keyboard navigation (left/right arrows)
- Include appropriate animation transitions
```

### 7.4 How to Use It

Claude will give you a long block of code → **copy all of it** → paste into a text editor (Mac's built-in TextEdit works) → **save as an `.html` file** (e.g., `presentation.html`) → double-click to open!

> 💡 **Tip**: When saving, TextEdit defaults to `.rtf` format. You need to: **Format → Make Plain Text**, then save with the `.html` extension. Or even simpler — in Terminal, use `touch presentation.html` to create an empty file, then open it with VS Code to edit.

### 7.5 Level Up: Make Your Webpage Look Even Better

You can add extra requests:
- "Use a gradient background"
- "Add a dark/light mode toggle button"
- "Use Chart.js for data visualization" (Claude will inline Chart.js too)

---

## 8. Drawing Data Charts with Python

Lab experiments, data analysis reports… a good chart is worth a thousand words. Let Claude write the Python code to draw them!

### 8.1 Basic Usage

```
Please write a Python script using matplotlib to draw [describe the chart you want].
Here's the data: [paste data]
Requirements: save as a PNG image at 300 DPI.
```

### 8.2 Complete Example

Say you want a simple line chart:

```
Please write a Python script using matplotlib to draw a line chart.
X-axis: months (January through December), Y-axis: temperature (Celsius):
[5, 8, 15, 20, 25, 30, 33, 32, 28, 22, 14, 8]
Requirements:
- Title: "2025 Monthly Average Temperature"
- Save as temperature.png
- If matplotlib isn't installed, please pip install it first
```

### 8.3 How to Run a Python Script

After Claude outputs the code, you need to:

```
Step 1: Save the code as a .py file
        (e.g., plot.py)

Step 2: In Terminal, cd to the file's directory

Step 3: Run it:
        python3 plot.py

Step 4: Open the generated image file to view
```

> ⚠️ If your Mac says `python3: command not found`, Python isn't installed.
> Easiest fix: go to [python.org](https://python.org), download the installer, and click "Continue" all the way through.

### 8.4 Quick Reference: Common Chart Types

| Chart Type | What to Tell Claude |
|-----------|-------------------|
| Line chart | "Draw a line chart" |
| Bar chart | "Draw a bar chart" |
| Pie chart | "Draw a pie chart" |
| Scatter plot | "Draw a scatter plot" |
| Histogram | "Draw a histogram" |
| Heatmap | "Draw a heatmap" |
| Multiple subplots | "Arrange two subplots side by side" |

> 💡 **Tip**: If Claude's code doesn't run, copy the **full error message** to it: "This code threw an error: `[paste error]`. Please fix it."

---

## 9. Why Does Claude Keep Asking Me Questions? — Plan Mode Explained

### 9.1 The First Time You See It, You Might Be Confused

As you use Claude Code, you might see **`"1 plan mode"`** displayed at the top, and the interface will pop up options for you to choose from. For example:

```
┌─────────────────────────────────────────────────┐
│  Claude wants to:                                │
│  Create 3 files, modify 2 files                  │
│                                                  │
│  [Accept]  [Reject]  [Modify]                    │
└─────────────────────────────────────────────────┘
```

You might be thinking: **"I just asked you to write an assignment. Why are you making ME make choices??"**

Don't worry — this is a good thing.

### 9.2 What Is Plan Mode?

Plan Mode is Claude's **"think first, act later"** mode. The number (like N = 1, 2, 3…) indicates which plan number this is.

It's like a **meticulous construction crew** — before knocking down a wall, they show you the blueprint first:

> "Boss, I'm planning to put a window in this wall. Here's the blueprint. Does it look good? If yes, I'll start."

### 9.3 What the Three Options Mean

| Button | Meaning | When to Pick It |
|--------|---------|----------------|
| **Accept** | "OK, go ahead as planned" | The plan looks reasonable |
| **Reject** | "No, wrong direction" | It's completely not what you wanted |
| **Modify** | "Direction is about right, but needs tweaks" | Mostly OK, details need adjustment |

### 9.4 Why Is This a Good Thing?

🎯 **Protects your files**: Claude won't act recklessly — it first tells you what it intends to do, and only acts after you confirm. No more "I asked it to fix Chapter 3 and it rewrote my entire thesis" disasters.

🎯 **Helps you quality-check**: Sometimes you might casually toss out a vague request; Plan Mode makes Claude "translate" it back to you first so you can correct it in time.

### 9.5 If You Don't Want to Choose Every Time…

If you trust Claude, you can directly add this to your input:

> **"Please proceed"** or **"Just do it directly"**

Claude will skip Plan Mode and get straight to work.

Similarly, if you want to **enter** Plan Mode:

> **"Give me a plan first. I'll confirm before you execute."**

> 💡 **Advice**: For **important tasks** (editing papers, modifying code, deleting files), let Claude lay out the plan in Plan Mode for you to review before executing. For **simple tasks** (asking a question, looking something up), just say "Please proceed" to save time.

---

## 10. Summary & Handy Prompt Templates

### 10.1 What You've Learned

| Skill | One-Line Recap |
|-------|---------------|
| Open Terminal (Mac) | `Command + Space` → type `terminal` |
| Open Terminal (Windows) | `Win key` → type `powershell` or `terminal` |
| Basic commands | `ls` / `cd` / `mkdir` / `cp` / `mv` / `rm` (works in PowerShell) |
| File paths | Finder shows display names; Terminal uses English names (Desktop, Downloads...) |
| Project folders | One folder per course, `cd` into it, then launch `claude` |
| Launch Claude | Type `claude` in Terminal |
| Exit Claude | `Ctrl + C` twice or `/exit` |
| Resume conversation | `/resume` to pick up past conversations |
| ESC "undo button" | Press once to interrupt, multiple times to rewind |
| Keyboard shortcuts | `Alt+Enter` for newline, `Alt+V` to paste images, `Cmd+C/V` copy/paste, `Ctrl+U` clear line |
| Let AI read files | Space + `@` + select files |
| Find tools | "Please search/install relevant skills or GitHub repos" |
| Install GitHub repos | Give Claude the repo URL — it clones and configures on its own |
| Install Skills | Give Claude a skills repo URL — extends Claude's capabilities |
| Troubleshooting | Just tell Claude directly — you don't need to know how to code |
| View .md files | VS Code (`Cmd+Shift+V`) / Spacebar Quick Look / Typora |
| LaTeX assignments | Claude writes `.tex` → compile on texpage.com → download PDF |
| HTML presentations | "Output a single HTML file with all CSS and JS inline" |
| Python charts | Claude writes `.py` → Terminal `python3` to run |
| Plan Mode | Review the plan first, then execute = safe + controlled |

### 10.2 Handy Prompt Templates (Copy & Adapt)

#### 📝 Assignment Writing

```
Please help me write a course assignment on [topic] with these requirements:
- Approximately [XXX] words
- Include abstract, introduction, body (3 sections), and conclusion
- Cite [X] references
- Output as LaTeX format (.tex file)
```

#### 📊 Data Analysis

```
Please analyze this dataset [@data-file.csv] with these requirements:
- First clean the data using Python
- Identify key trends
- Draw 3 relevant charts
- Write an analysis summary
If any tools are missing, please search for and install them automatically
```

#### 🐛 Code Debugging

```
This code [@code-file] threw an error when running. Here's the error:
[paste error message]
Please find the issue and fix it
```

#### 🎨 Report Generation

```
Please generate a complete lab report based on [@experiment-data] with these requirements:
- LaTeX format
- Include purpose, methods, results, and discussion
- Draw data charts using Python matplotlib (provide the code as well)
- Embed chart images in the LaTeX document
```

#### 🌐 Presentation Document

```
Please generate a classroom presentation document with these requirements:
- Output a single HTML file with all CSS and JS code inline, zero external dependencies
- Topic: [your subject]
- 8-10 slides with keyboard navigation
- Style: clean and modern, suitable for projector display
- If there are formulas, use MathJax (inlined)
```

---

### 🎓 One Last Thing

Claude Code is like **a TA with infinite patience** — you can ask it anything, have it do anything for you, and even talk to yourself through it to clarify your thoughts.

It might feel a bit disorienting at first (command line, Plan Mode, all these options…), but after using it a few times, you'll discover: **homework can actually be this easy!**

> 💬 **Don't forget the most important principle**: **Clearly state what you want, and let Claude figure out the rest.** Don't have the right tool? Let it install one. Don't have the knowledge? Let it look it up. Your job is just to be the "person who asks the questions."

Happy Coding! 🎉

---

*This document was generated by Claude Code · June 2026*
