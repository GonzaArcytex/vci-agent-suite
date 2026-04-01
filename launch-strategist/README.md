# Launch Strategist — Installation & Usage

This agent turns a freshly built app into a 30-day GTM plan. It asks you 7 targeted questions about your app, your audience, and your channels — then produces a specific, channel-first action plan with weekly tasks and KPIs.

---

## What You'll Get

A Markdown file saved to `outputs/launch-plan-[appname]-[date].md` containing:
- App positioning one-liner and ICP description
- Primary and secondary channel recommendations (based on your actual traction)
- 30-day action plan broken into 4 themed weeks
- 3 KPIs to track
- Quick wins to execute in the first 48 hours

---

## How to Install

You don't install anything. This agent runs entirely inside Claude Code.

The only requirement is that **Claude Code is installed** on your machine. If you completed the VCI workshop, it already is.

---

## How to Open the Agent

### Option A — VS Code (recommended)

1. Open VS Code
2. Go to `File → Open Folder`
3. Navigate to the `launch-strategist` folder and click **Select Folder**
4. Open the Claude Code panel (left sidebar or `Ctrl+Shift+P` → "Claude Code")
5. Start a new session — the agent will introduce itself automatically

### Option B — Terminal

```bash
cd path/to/vci-agent-suite/launch-strategist
claude
```

Replace `path/to/vci-agent-suite` with the actual path on your machine.

---

## How to Use It

1. **Start the session.** The agent reads its instructions and introduces itself.
2. **Answer the questions.** It will ask 7 questions, one at a time. Answer honestly — the more specific you are, the better your plan will be.
3. **Get your plan.** Once all 7 questions are answered, the agent builds your 30-day GTM plan and saves it to `outputs/`.
4. **Find your file.** Open `outputs/launch-plan-[yourappname]-[date].md` to see the full plan.

> **Tip:** The agent remembers you across sessions. The second time you use it, it will already know your ICP and channels — you won't have to repeat yourself.

---

## What the 7 Questions Cover

1. What does your app do?
2. Who is it for? (specific ICP)
3. What problem does it solve, and what does inaction cost?
4. Do you have an existing audience?
5. Which channels do you currently use or have traction on?
6. What's your launch timeline?
7. Organic only, or open to paid ads?

The agent will not produce output until all 7 are answered.

---

## Where Your Output Is Saved

All outputs go to the `outputs/` folder inside this agent directory.

Filename format: `launch-plan-[appname]-[date].md`

Example: `outputs/launch-plan-coachflow-2026-04-01.md`

> Note: The `outputs/` folder is excluded from git (`.gitignore`). Your plans stay private on your machine.

---

## Troubleshooting

**The agent isn't following the instructions.**
Make sure you opened the `launch-strategist` folder directly — not the parent `vci-agent-suite` folder. Claude Code reads the `CLAUDE.md` in whichever folder you open.

**The agent forgot our previous conversation.**
Memory is stored in `memory/launch-strategist-memory.md`. If something went wrong, you can open that file and check what was saved. You can also edit it manually to correct anything.

**I want to start fresh.**
Delete or clear the contents of `memory/launch-strategist-memory.md` and start a new session.
