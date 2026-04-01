# VCI Agent Suite

Three standalone Claude Code agents for VCI (VibeCode Incubator) founding members. These are VIP bonuses for coaches, consultants, and agency owners who just built their first app with Claude Code and need to launch, package, and brand it.

Each agent is **standalone** — no orchestrator. Open the agent's folder directly in Claude Code and talk to it. It runs an intake interview and saves your deliverables to its own `outputs/` folder.

---

## The Agents

### 1. Launch Strategist
**Folder:** `launch-strategist/`

Turns a freshly built app into a 30-day GTM plan. Asks 7 targeted questions about your app, your audience, and your channels — then produces a specific, channel-first action plan with weekly tasks and KPIs.

**Use it when:** You just finished building and have no idea how to get your first users.

**Output:** `outputs/launch-plan-[appname]-[date].md`

---

### 2. Offer Architect
**Folder:** `offer-architect/`

Builds a complete, ready-to-sell offer document. Asks 8 questions about your product, your buyer, and your pricing — then produces a full offer doc with positioning, pricing rationale, objection handlers, and sales page headlines.

**Use it when:** You don't know how to package or price your app, or your current offer isn't converting.

**Output:** `outputs/offer-doc-[appname]-[date].md`

---

### 3. Brand Voice
**Folder:** `brand-voice/`

Captures your unique voice and produces two files: a Brand Voice Profile and a ready-to-install Claude Code skill file. Once installed, every future Claude build will sound like you automatically.

**Use it when:** AI-generated output doesn't sound like you — landing pages, emails, and social posts all feel generic.

**Outputs:**
- `outputs/brand-voice-profile-[name]-[date].md`
- `outputs/brand-voice-skill.md` ← install this in `~/.claude/skills/` to apply your voice everywhere

---

## How to Use Each Agent

Each agent is a self-contained Claude Code project. Use them independently — you don't need to open all three at once.

### Step 1 — Open the agent folder in Claude Code

**Option A — VS Code:**
```
File → Open Folder → select the agent folder (e.g. launch-strategist/)
Then open the Claude Code panel and start a new session.
```

**Option B — Terminal:**
```bash
cd path/to/vci-agent-suite/launch-strategist
claude
```

### Step 2 — Talk to the agent

The agent will read its memory file, introduce itself, and begin the intake interview. Answer the questions one at a time. When the intake is complete, the agent produces your output and saves it to `outputs/`.

### Step 3 — Find your output

All deliverables are saved to the agent's `outputs/` folder with a timestamped filename. Open the file in VS Code or any Markdown viewer.

---

## Installing the Brand Voice Skill (Brand Voice agent only)

After running the Brand Voice agent, you'll have a file called `brand-voice-skill.md` in `brand-voice/outputs/`. To install it:

1. Copy the file to `~/.claude/skills/brand-voice-[yourname]/SKILL.md`
2. That's it — every future Claude Code session will automatically apply your voice to any content task

---

## Suite Structure

```
vci-agent-suite/
  README.md                               ← This file
  .gitignore
  launch-strategist/
    CLAUDE.md                             ← Role, memory protocol, rules
    skills/launch-strategist/SKILL.md    ← Full workflow and output template
    memory/launch-strategist-memory.md   ← Persistent memory (agent fills in)
    workflows/                            ← Reserved for future automation
    outputs/                              ← Your launch plans go here
  offer-architect/
    CLAUDE.md
    skills/offer-architect/SKILL.md
    memory/offer-architect-memory.md
    workflows/
    outputs/
  brand-voice/
    CLAUDE.md
    skills/brand-voice/SKILL.md
    memory/brand-voice-memory.md
    workflows/
    outputs/
```

---

*VCI Agent Suite v1.0 — Built for VibeCode Incubator founding members*
