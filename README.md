# VCI Agent Suite

**A VIP bonus for VibeCode Incubator founding members.**

Three AI agents built inside Claude Code — each one a specialist that helps you turn your freshly built app into a real business. No extra software, no subscriptions, no setup beyond what you already have from the VCI workshop.

---

## What's Inside

| Agent | What It Does | Use It When... |
|-------|-------------|----------------|
| **Launch Strategist** | Builds a 30-day GTM plan | You finished building and don't know how to get your first users |
| **Offer Architect** | Builds a complete offer document | You don't know how to package or price your app |
| **Brand Voice** | Captures your voice + creates an installable Claude skill | Your AI-generated content doesn't sound like you |

Each agent runs an intake interview and saves your deliverables to its own `outputs/` folder on your machine.

---

## Requirements

Before you start, make sure you have:

- **Claude Code** installed — if you completed the VCI workshop, you already have this
- **VS Code** installed (recommended for opening agents)
- A **Claude Pro or API** account (required to run Claude Code)

If you need to install Claude Code: open your terminal and run:
```bash
npm install -g @anthropic-ai/claude-code
```

---

## How These Agents Work

Each agent is a folder. When you open that folder in Claude Code, Claude reads the instructions inside and immediately knows how to behave as that specific agent — what to ask, in what order, what to produce, and where to save it.

You don't run any code. You just open a folder and have a conversation.

---

## Getting Started — Step by Step

### Step 1 — Download or clone this repo

**Option A — Download as ZIP (simplest)**
Click the green **Code** button at the top of this page → **Download ZIP** → unzip it somewhere on your computer.

**Option B — Clone with git**
```bash
git clone https://github.com/[repo-url]/vci-agent-suite.git
cd vci-agent-suite
```

### Step 2 — Pick an agent and open its folder

Open VS Code. Go to `File → Open Folder`. Navigate inside the downloaded folder and select **one agent folder** — for example, `launch-strategist`.

> Important: open the agent's folder directly, not the whole `vci-agent-suite` folder. Claude Code reads the instructions in whichever folder you open.

### Step 3 — Start a Claude Code session

Open the Claude Code panel in VS Code (look for it in the left sidebar, or press `Ctrl+Shift+P` and search for "Claude Code"). Start a new conversation.

The agent will introduce itself and begin the intake interview.

### Step 4 — Answer the questions

Each agent asks a series of questions, one at a time. Answer honestly and specifically — the more detail you give, the better your output will be.

### Step 5 — Find your output

When the agent is done, it saves a Markdown file to the `outputs/` folder inside the agent directory. Open it in VS Code or any Markdown viewer.

---

## The Three Agents

### Launch Strategist
**Folder:** `launch-strategist/`

Asks 7 questions about your app, your audience, and your channels. Produces a 30-day GTM plan with weekly tasks, channel recommendations based on your actual traction, 3 KPIs, and quick wins for the first 48 hours.

**Output:** `outputs/launch-plan-[appname]-[date].md`

→ See [launch-strategist/README.md](launch-strategist/README.md) for full instructions.

---

### Offer Architect
**Folder:** `offer-architect/`

Asks 8 questions about your product, your buyer, and your pricing. Produces a complete offer document — positioning, pricing rationale, value stack, guarantee, objection handlers, and sales page headlines. Will tell you if you're undercharging.

**Output:** `outputs/offer-doc-[appname]-[date].md`

→ See [offer-architect/README.md](offer-architect/README.md) for full instructions.

---

### Brand Voice
**Folder:** `brand-voice/`

Captures your voice through writing samples or an 8-question interview. Produces a Brand Voice Profile and a ready-to-install Claude Code skill file. Install the skill once and every future Claude build will automatically sound like you.

**Outputs:**
- `outputs/brand-voice-profile-[name]-[date].md`
- `outputs/brand-voice-skill.md` ← install this in `~/.claude/skills/` to apply your voice everywhere

→ See [brand-voice/README.md](brand-voice/README.md) for full instructions including skill installation.

---

## Tips for Best Results

**Be specific in your answers.** "Female health coaches who sell 1:1 programs" is better than "coaches." The more specific you are, the more specific (and useful) your output will be.

**Each agent remembers you.** After your first session, the agent saves key details to a memory file. Next time you open it, it already knows your ICP, your channels, your voice — you won't have to repeat yourself.

**Use them in order.** If you're starting from scratch: Brand Voice → Offer Architect → Launch Strategist. That way your launch plan and offer already reflect your voice.

**Outputs stay private.** The `outputs/` folders are excluded from git. Your deliverables never leave your machine unless you choose to share them.

---

## Folder Structure

```
vci-agent-suite/
  README.md                                    ← This file
  .gitignore
  launch-strategist/
    README.md                                  ← Install & usage guide
    CLAUDE.md                                  ← Agent instructions (read by Claude)
    skills/launch-strategist/SKILL.md         ← Full workflow and output template
    memory/launch-strategist-memory.md        ← Persistent memory (agent fills in)
    workflows/                                 ← Reserved for future use
    outputs/                                   ← Your launch plans go here
  offer-architect/
    README.md
    CLAUDE.md
    skills/offer-architect/SKILL.md
    memory/offer-architect-memory.md
    workflows/
    outputs/
  brand-voice/
    README.md
    CLAUDE.md
    skills/brand-voice/SKILL.md
    memory/brand-voice-memory.md
    workflows/
    outputs/
```

---

## Troubleshooting

**Claude isn't behaving like the agent.**
Make sure you opened the agent's subfolder directly (e.g. `launch-strategist/`), not the root `vci-agent-suite/` folder.

**I don't see the Claude Code panel in VS Code.**
Install the Claude Code extension: open VS Code → Extensions (`Ctrl+Shift+X`) → search "Claude Code" → Install.

**The agent forgot our last conversation.**
Each agent's memory lives in its `memory/` folder. Open the `.md` file there to see what was saved. You can also edit it manually.

---

*VCI Agent Suite v1.0 — Built for VibeCode Incubator founding members*
