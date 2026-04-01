# Brand Voice — Installation & Usage

This agent captures your unique communication style and produces two deliverables: a Brand Voice Profile you can reference, and a ready-to-install Claude Code skill file so every future Claude build automatically sounds like you.

---

## What You'll Get

**File 1: `outputs/brand-voice-profile-[name]-[date].md`**
A complete profile of your voice including tone descriptors, vocabulary (what to use and what to never use), sentence and structure patterns, writing do's and don'ts, example phrases, and a "sounds like" reference point.

**File 2: `outputs/brand-voice-skill.md`**
A working Claude Code skill file in the correct format. Install it once and every future Claude session will apply your voice automatically to any content task — emails, social posts, landing pages, scripts, captions.

---

## How to Install

You don't install anything to run this agent. It runs entirely inside Claude Code.

The only requirement is that **Claude Code is installed** on your machine. If you completed the VCI workshop, it already is.

---

## How to Open the Agent

### Option A — VS Code (recommended)

1. Open VS Code
2. Go to `File → Open Folder`
3. Navigate to the `brand-voice` folder and click **Select Folder**
4. Open the Claude Code panel (left sidebar or `Ctrl+Shift+P` → "Claude Code")
5. Start a new session — the agent will introduce itself automatically

### Option B — Terminal

```bash
cd path/to/vci-agent-suite/brand-voice
claude
```

Replace `path/to/vci-agent-suite` with the actual path on your machine.

---

## How to Use It

1. **Start the session.** The agent introduces itself and asks which intake mode you prefer.
2. **Choose your intake mode:**
   - **Mode A (Content):** Paste 3–5 examples of your own writing — emails, social posts, captions, anything you've actually written. The more casual the better.
   - **Mode B (Interview):** Answer 8 questions about your style, audience, vocabulary, and tone.
3. **Review and confirm.** The agent drafts a voice profile and shows it to you. If something feels off, tell it — it will refine until you say "that's me."
4. **Get your files.** Once you confirm the profile, the agent produces both output files and saves them to `outputs/`.

> **Tip:** Mode A (pasting real writing samples) usually produces a more accurate result because it captures how you actually write, not just how you think you write.

---

## How to Install the Brand Voice Skill

After running this agent, you'll have a file at `outputs/brand-voice-skill.md`. Here's how to install it so every future Claude session uses your voice:

**Step 1 — Create the skills folder (if it doesn't exist)**

On Windows (Git Bash or PowerShell):
```bash
mkdir -p ~/.claude/skills/brand-voice-[yourname]
```

**Step 2 — Copy the skill file**
```bash
cp outputs/brand-voice-skill.md ~/.claude/skills/brand-voice-[yourname]/SKILL.md
```

Replace `[yourname]` with your actual name (e.g. `brand-voice-gonzalo`).

**Step 3 — That's it.**

From now on, whenever you ask Claude to write content — a landing page, an email, a social post — it will apply your voice automatically. You can also explicitly trigger it by saying "write this in my voice" or "make this sound like me."

---

## Where Your Output Is Saved

All outputs go to the `outputs/` folder inside this agent directory.

| File | Description |
|------|-------------|
| `brand-voice-profile-[name]-[date].md` | Your full voice profile — keep this as a reference |
| `brand-voice-skill.md` | The installable skill file — copy this to `~/.claude/skills/` |

> Note: The `outputs/` folder is excluded from git (`.gitignore`). Your voice profile stays private on your machine.

---

## Updating Your Voice Profile

Your voice evolves. Come back to this agent any time to:
- Refine the profile based on feedback ("this still doesn't sound right")
- Add new vocabulary or phrases you've started using
- Update the skill file after changes

The agent remembers your existing profile and will ask if you want to refine it or start fresh.

---

## Troubleshooting

**The agent isn't following the instructions.**
Make sure you opened the `brand-voice` folder directly — not the parent `vci-agent-suite` folder. Claude Code reads the `CLAUDE.md` in whichever folder you open.

**The agent forgot my voice profile.**
The profile is stored in `memory/brand-voice-memory.md`. Open that file to check what was saved. If it's blank or incomplete, re-run the intake.

**The installed skill isn't applying my voice.**
Make sure the file is at exactly `~/.claude/skills/brand-voice-[yourname]/SKILL.md` — the folder name and filename both matter.
