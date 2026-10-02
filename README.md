# Qubit Code

A desktop coding agent for Windows. You give it a folder and a task, and it reads your code, edits files, runs commands and checks its own work while you watch. It runs on your [Qubit](https://qubitai.cc) API key, so one key gets you models from Google, OpenAI, Anthropic, DeepSeek, Qwen, Meta and more.

> **Beta.** This is version 0.1.0. Expect rough edges, and please report anything that breaks.

## Install

1. Download `Qubit Code_0.1.0_x64-setup.exe` from the [latest release](../../releases/latest).
2. Run it. Windows will probably say "Windows protected your PC" because the installer isn't code signed yet. Click **More info**, then **Run anyway**.
3. Open Qubit Code from the Start menu.

You need Windows 10 or 11 (64-bit). The app uses Microsoft Edge WebView2, which Windows 11 already has. On Windows 10 the installer fetches it if it's missing.

There's also an `.msi` in the release if you'd rather install that way.

## Getting started

1. **Add your key.** The first screen asks for your Qubit API key. Get one from your account at [qubitai.cc](https://qubitai.cc), paste it in, and click **Save and test**. Qubit checks the key straight away so you know it works.
2. **Open a folder.** Click **+** next to Workspaces in the sidebar and choose the project folder you want to work on. The agent can only touch files inside the folders you give it.
3. **Ask for something.** Type a task in the message box, like "add a dark mode toggle to the settings page" or "why does the login test fail?", and press Enter.

The agent works through the task step by step. You'll see each file it reads, each edit and each command as it happens, and you can click any step to see exactly what went in and out.

## Staying in control

You pick how much the agent can do on its own from the chip under the message box:

| Mode | What happens |
|---|---|
| Ask before changes | It reads freely but asks before editing files or running commands. This is the default. |
| Edit automatically | It edits files in your workspace without asking, but still asks before deleting files or running commands. |
| Plan mode | It looks around and writes a plan, without changing anything. |
| Full access | It does everything without asking. Use this only in a folder you don't mind it changing. |

When it asks, you can allow once, always allow that kind of action, or deny. You can stop a turn at any time, and **Checkpoints** let you roll back the files a turn changed.

For finer control, **Sandbox** rules can block or allow specific commands, paths and websites.

## What's in it

**The agent**
- Reads, writes and edits files, searches your code, and runs PowerShell commands.
- Uses a real browser to open pages, click around and check its work.
- Hands parts of a big job to subagents and keeps track of what they're doing.
- Sets goals for a session and remembers notes you want it to keep.
- Reads project notes files (`QUBIT.md`, `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, `.cursorrules` and others) so it follows your project's rules.

**The side panel**
- **Terminal** (`` Ctrl+` ``): your own PowerShell in the project folder. You can let the agent see what you run, or keep it private.
- **Browser** (`Ctrl+T`): a built-in browser next to your chat.
- **Side chat** (`Ctrl+Alt+S`): ask a quick question about the current chat without derailing it.

**Models**
- Dozens of models through one Qubit key, with prices shown per million tokens.
- Switch models from the message box at any time.
- **Routing** sends different kinds of tasks to different models, and **Compare** asks two models the same thing side by side.
- **Budgets** cap what you spend, and the sidebar shows what you've spent today.

**Extending it**
- **Plugins** and **Skills** add commands, instructions and tools. You can import skills you already use.
- **MCP servers** connect outside tools, and Qubit can run as an MCP server itself.
- **Hooks** run your own scripts when the agent does certain things.
- **Automations** run a prompt on a schedule, like a nightly dependency check.

**Everyday stuff**
- Attach images, PDFs and code files, or paste a screenshot straight into the message box.
- Talk instead of typing with voice dictation.
- Slash commands: type `/` for `/compact`, `/model`, `/commit`, `/export` and more.
- Dark, light and Glass themes. Glass makes the window see-through, with your desktop blurred behind it.
- A global quick entry key brings Qubit up from any app with a new chat ready.
- **Sync and backup** saves your chats to a password-protected backup file.

## Shortcuts

| Keys | Does |
|---|---|
| `Ctrl+N` | New chat |
| `Ctrl+K` | Search chats and commands |
| `Ctrl+B` | Show or hide the sidebar |
| `Ctrl+T` | Open the browser panel |
| `` Ctrl+` `` | Open the terminal |
| `Ctrl+Alt+S` | Open side chat |
| `Ctrl+=` / `Ctrl+-` / `Ctrl+0` | Zoom in, out, reset |

Type `/shortcuts` in the message box for the full list.

## Your data

- Your API key, chats and settings are stored on your computer. Nothing goes through a Qubit Code server.
- Your messages go to the Qubit API so the model can answer them, and only to the model you picked.
- The agent can only see the folders you've added as workspaces, unless you turn that off in Settings.
- Settings has a storage section that shows how much space your chats use and lets you clear things out.

## Known issues

- The installer isn't signed yet, so you'll see the SmartScreen warning on install.
- Windows only for now.
- Web pages in the browser panel always show on a solid background, even in the Glass theme.

## Reporting bugs

Open an [issue](../../issues) and include:
- what you did, step by step;
- what you expected to happen;
- what happened instead, with a screenshot if you can.

Please don't paste your API key into an issue.
