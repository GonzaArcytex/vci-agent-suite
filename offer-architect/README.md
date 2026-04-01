# Offer Architect — Installation & Usage

This agent builds a complete, ready-to-sell offer document for your app or service. It asks 8 questions about your product, your buyer, and your pricing — then produces a full offer doc with positioning, pricing rationale, a value stack, objection handlers, and sales page headlines.

---

## What You'll Get

A Markdown file saved to `outputs/offer-doc-[appname]-[date].md` containing:
- A positioning one-liner (dream buyer + transformation + without the hard part)
- Dream buyer description
- Before/after transformation (quantified where possible)
- Recommended price with reasoning anchored against alternatives
- What's included, what's not, and why
- A guarantee statement
- 3 scripted objection handlers
- 3 sales page headline options

---

## How to Install

You don't install anything. This agent runs entirely inside Claude Code.

The only requirement is that **Claude Code is installed** on your machine. If you completed the VCI workshop, it already is.

---

## How to Open the Agent

### Option A — VS Code (recommended)

1. Open VS Code
2. Go to `File → Open Folder`
3. Navigate to the `offer-architect` folder and click **Select Folder**
4. Open the Claude Code panel (left sidebar or `Ctrl+Shift+P` → "Claude Code")
5. Start a new session — the agent will introduce itself automatically

### Option B — Terminal

```bash
cd path/to/vci-agent-suite/offer-architect
claude
```

Replace `path/to/vci-agent-suite` with the actual path on your machine.

---

## How to Use It

1. **Start the session.** The agent reads its instructions and introduces itself.
2. **Answer the questions.** It will ask 8 questions, one at a time. Be honest about your pricing instincts — the agent will tell you if you're undercharging and explain why.
3. **Get your offer doc.** Once all 8 questions are answered, the agent builds your complete offer document and saves it to `outputs/`.
4. **Find your file.** Open `outputs/offer-doc-[yourappname]-[date].md` to see the full document.

> **Tip:** The agent remembers your ICP and pricing history across sessions. If you come back to refine an offer, it will pick up where you left off.

---

## What the 8 Questions Cover

1. What does your app do?
2. Who is the dream buyer? (specific — job title, situation, current struggle)
3. What does their problem look like before your app?
4. What does life/business look like 30 days after using it?
5. What alternatives do they have — including doing nothing or hiring someone?
6. What are you thinking of charging?
7. What objections do you expect?
8. How are you selling this — SaaS, one-time purchase, or done-for-you?

The agent will not produce output until all 8 are answered.

---

## Where Your Output Is Saved

All outputs go to the `outputs/` folder inside this agent directory.

Filename format: `offer-doc-[appname]-[date].md`

Example: `outputs/offer-doc-coachflow-2026-04-01.md`

> Note: The `outputs/` folder is excluded from git (`.gitignore`). Your offer documents stay private on your machine.

---

## Troubleshooting

**The agent isn't following the instructions.**
Make sure you opened the `offer-architect` folder directly — not the parent `vci-agent-suite` folder. Claude Code reads the `CLAUDE.md` in whichever folder you open.

**The agent forgot our previous conversation.**
Memory is stored in `memory/offer-architect-memory.md`. Open that file to check what was saved, or edit it manually to correct anything.

**I want to start fresh.**
Delete or clear the contents of `memory/offer-architect-memory.md` and start a new session.
