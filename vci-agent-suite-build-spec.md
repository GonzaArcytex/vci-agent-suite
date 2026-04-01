# VCI Agent Suite — Build Specification
<!-- Hand this file to Claude Code and run the prompt at the bottom -->

---

## What We're Building

Three standalone Claude Code agents delivered as a folder called `vci-agent-suite`. These are VIP bonuses for VCI (VibeCode Incubator) founding members — coaches, consultants, and agency owners who just built their first vibe-coded app with Claude Code.

Each agent is **standalone** — no orchestrator, no Donna. The user opens the agent's folder directly in Claude Code and talks to it. The agent runs an intake interview and saves outputs to its own `outputs/` folder.

The reference architecture comes from the `my-ai-team` starter kit (structure below). Match that format exactly.

---

## Reference Architecture (from starter kit)

```
[agent-name]/
  CLAUDE.md                         ← Role, memory protocol, rules, how to start
  skills/[agent-name]/
    SKILL.md                        ← Full operational guide, trigger phrases, workflows, output format
  memory/
    [agent-name]-memory.md          ← Persistent memory template (agent fills in over time)
  workflows/                        ← Empty folder (reserved for future)
  outputs/                          ← Where the agent saves all deliverables
```

**Starter kit CLAUDE.md format to match:**
- H2: Role, Specialties, Memory, Rules
- Memory protocol: read memory file at session start, update at session end
- Rules: bullet list of absolute constraints

**Starter kit SKILL.md format to match:**
- YAML frontmatter: name, description (trigger phrases go here)
- H2 sections: Role, Trigger Phrases, Intake Process, Workflows, Output Format, Memory Protocol, Rules
- Output format always includes a clear template the agent must follow
- Always ends with a Self-Evaluation Checklist

---

## Agent 1 — Launch Strategist

**Folder:** `launch-strategist/`

**One-line role:** Turns a freshly built app into a 30-day GTM plan.

**Who uses it:** VCI founding members who just finished the Claude Code workshop and built their first app. They have the app. They don't know how to get their first users.

**Trigger phrases (for SKILL.md description frontmatter):**
- "how do I get my first users"
- "I just launched, now what"
- "help me market my app"
- "I need a launch plan"
- "how do I go to market"
- "create a GTM plan"
- "what do I do after I build"

**Intake interview — 7 questions, in this exact order, one at a time:**
1. What does your app do? Describe it in one sentence.
2. Who is it for? Describe the dream user specifically (not "entrepreneurs" — think "female health coaches who sell 1:1 programs online").
3. What problem does it solve, and what does it cost the user to leave that problem unsolved?
4. Do you already have an audience? (email list size, social following, community, existing clients — be honest)
5. Which channels do you currently use or have traction on? (YouTube, Instagram, LinkedIn, Facebook groups, email, podcast, etc.)
6. What's your launch timeline? When do you need your first users?
7. Are you willing to spend on paid ads now, or do you need this to be organic only?

**Never produce output before all 7 questions are answered.**

**Output — one file saved to `outputs/launch-plan-[appname]-[date].md`:**
```
# Launch Plan — [App Name]
Generated: [date]

## App Positioning
**One-liner:** [problem] → [solution] → [transformation]
**ICP:** [specific description of ideal customer]

## Channel Strategy
**Primary channel:** [the one they should go all-in on first, based on their existing traction]
**Secondary channel:** [supporting channel]
**Paid ads:** [yes/not yet + reasoning]

## 30-Day Action Plan

### Week 1 — Foundation (Days 1–7)
- [ ] [specific task]
- [ ] [specific task]
- [ ] [specific task]

### Week 2 — Launch (Days 8–14)
- [ ] [specific task]
- [ ] [specific task]

### Week 3 — Push (Days 15–21)
- [ ] [specific task]
- [ ] [specific task]

### Week 4 — Optimize (Days 22–30)
- [ ] [specific task]
- [ ] [specific task]

## 3 KPIs to Track
1. [metric] — target: [number] by day 30
2. [metric] — target: [number] by day 30
3. [metric] — target: [number] by day 30

## Quick Wins (do these in the first 48 hours)
- [action]
- [action]
- [action]
```

**Memory stores:** user's ICP, their channels and traction levels, past launch attempts, what worked for them before.

---

## Agent 2 — Offer Architect

**Folder:** `offer-architect/`

**One-line role:** Builds a complete, ready-to-sell offer document for any app or service.

**Who uses it:** VCI founding members who built an app and don't know how to package or price it — or whose offer "isn't converting" and they don't know why.

**Framework:** Apply Alex Hormozi's $100M Offers methodology throughout — dream outcome, perceived likelihood of achievement, time delay, effort and sacrifice. Never name-drop the framework to the user. Just apply it.

**Trigger phrases:**
- "help me price my app"
- "how do I package this"
- "I don't know what to charge"
- "help me make an offer"
- "how do I position this"
- "what should I include"
- "my offer isn't converting"
- "create an offer document"

**Intake interview — 8 questions, in order, one at a time:**
1. What does your app do? One sentence.
2. Who is the dream buyer? Be specific — job title, situation, what they're struggling with right now.
3. What does their problem look like before they find your app? What are they doing/feeling/losing?
4. What does their life or business look like 30 days after using your app? What's the transformation?
5. What alternatives do they have — including doing nothing, hiring someone, or using a competitor?
6. What have you been thinking of charging? Or what feels right to you?
7. What objections do you expect? ("Too expensive", "I don't have time to set it up", "I've tried tools like this before", etc.)
8. How are you selling this — SaaS subscription, one-time purchase, or done-for-you service?

**Never produce output before all 8 questions are answered.**

**Output — one file saved to `outputs/offer-doc-[appname]-[date].md`:**
```
# Offer Document — [App/Product Name]
Generated: [date]

## The One-Liner
[Dream buyer] who [specific problem] can now [transformation] without [biggest objection/effort], even if [biggest limiting belief].

## Dream Buyer
[2-3 sentence specific description]

## The Transformation
**Before:** [specific before state]
**After:** [specific after state — quantified where possible]

## Recommended Pricing
**Price:** $[amount] [per month / one-time / etc.]
**Why this number:** [reasoning anchored against alternatives and perceived value of transformation]
**Anchoring:** [what the alternatives cost — doing nothing, hiring someone, competitor]

## What's Included
**Core:**
- [main deliverable]

**Value adds:**
- [bonus/add-on 1] — [why it's valuable]
- [bonus/add-on 2] — [why it's valuable]

**What's NOT included (and why):**
- [excluded item] — [reason — often sharpens the offer]

## The Guarantee
[Specific guarantee statement — what you promise and what happens if it's not delivered]

## Objection Handlers
**Objection 1: "[exact objection]"**
Response: [scripted reply]

**Objection 2: "[exact objection]"**
Response: [scripted reply]

**Objection 3: "[exact objection]"**
Response: [scripted reply]

## Suggested Sales Page Headline
Option A: [headline]
Option B: [headline]
Option C: [headline]
```

**Memory stores:** user's ICP, pricing history, past offers and whether they converted, audience pain points and objections.

---

## Agent 3 — Brand Voice

**Folder:** `brand-voice/`

**One-line role:** Captures the user's unique voice and produces a Brand Voice Profile + a ready-to-install Claude Code skill file so every future Claude build sounds like them.

**Who uses it:** VCI founding members who keep getting AI-generated output that doesn't sound like them — landing pages, emails, social posts all sound generic. This agent fixes it permanently.

**Why it's special:** The output includes a working `brand-voice-skill.md` in valid Claude Code skill format. The user installs it once in their `~/.claude/skills/` folder and every future Claude build inherits their voice automatically.

**Trigger phrases:**
- "this doesn't sound like me"
- "help me capture my brand voice"
- "I want Claude to write like me"
- "create a voice profile"
- "my content sounds too AI"
- "train you on my style"
- "create a brand voice skill"

**Intake — two modes. Ask the user which they prefer before starting:**

**Mode A — Content Ingestion:**
Ask the user to paste 3–5 examples of their own writing (emails, social posts, captions, anything). Then:
1. Analyze and extract: tone, sentence length patterns, vocabulary choices, recurring phrases, humor/formality level, what they never say
2. Produce a draft voice profile
3. Present it to the user and ask: "Does this capture your voice? Is there anything that feels off?"
4. Refine based on feedback until the user confirms it's right
5. Lock it in and produce outputs

**Mode B — Interview:**
Ask these 8 questions one at a time:
1. Describe your communication style in 3 words.
2. Who is your audience — who are you always talking to? Be specific.
3. What topics do you cover in your content or communications?
4. What words or phrases do you use constantly? (even slang, filler phrases, sign-offs)
5. What words or phrases do you never use — things that would sound wrong coming from you?
6. What's your tone? Pick 2–3: direct / conversational / educational / inspirational / authoritative / casual / funny / no-nonsense / warm / bold
7. Who do you sound like — any creator, author, or speaker you've been compared to or admire?
8. What do you want people to feel after reading your content?

**Never produce output before the intake is complete and user has confirmed.**

**Output — TWO files saved to `outputs/`:**

**File 1: `brand-voice-profile-[name]-[date].md`**
```
# Brand Voice Profile — [Name / Brand]
Generated: [date]

## Voice in One Paragraph
[2-3 sentence description of how this person writes and what makes them distinct]

## Tone Descriptors
[List of 3-5 adjectives that describe the voice]

## Vocabulary
**Use freely:**
- [phrase/word]
- [phrase/word]

**Never use:**
- [phrase/word]
- [phrase/word]

## Sentence & Structure Patterns
- [observation about sentence length, paragraph length, use of lists etc.]
- [observation about how they open and close]

## Writing Do's
- [specific instruction]
- [specific instruction]

## Writing Don'ts
- [specific instruction]
- [specific instruction]

## Example Phrases (in their voice)
- "[example]"
- "[example]"
- "[example]"

## Sounds Like
[Reference point — who they sound like or the intersection of two references]
```

**File 2: `brand-voice-skill.md`** — must be in valid Claude Code skill format:
```
---
name: brand-voice-[name]
description: >-
  Apply [Name]'s brand voice to any content. Use this skill whenever writing
  emails, social posts, landing pages, scripts, captions, or any content that
  should sound like [Name]. Trigger when asked to "write in my voice",
  "make this sound like me", "write a [content type]", or any content creation task.
---

# Brand Voice Skill — [Name]

## Voice Profile
[Condensed version of the profile — tone, vocabulary rules, do's/don'ts]

## Always Do
- [rule]
- [rule]

## Never Do
- [rule]
- [rule]

## Vocabulary Quick Reference
Use: [word], [word], [word]
Avoid: [word], [word], [word]

## Before Writing Any Content
1. Read the voice profile above
2. Ask: what is this content for and who will read it?
3. Draft in [Name]'s voice
4. Check against the Never Do list before returning

## Self-Check Before Returning Output
- [ ] Does this sound like [Name] — not generic AI?
- [ ] Did I avoid all words/phrases on the Never list?
- [ ] Is the tone consistent throughout?
- [ ] Would [Name] actually say this?
```

**Memory stores:** The full captured voice profile. This IS the agent's primary value. Memory file is populated after first session and read every subsequent session.

---

## Folder Structure to Create

```
vci-agent-suite/
  README.md
  launch-strategist/
    CLAUDE.md
    skills/launch-strategist/
      SKILL.md
    memory/
      launch-strategist-memory.md
    workflows/
    outputs/
  offer-architect/
    CLAUDE.md
    skills/offer-architect/
      SKILL.md
    memory/
      offer-architect-memory.md
    workflows/
    outputs/
  brand-voice/
    CLAUDE.md
    skills/brand-voice/
      SKILL.md
    memory/
      brand-voice-memory.md
    workflows/
    outputs/
```

---

## Quality Bar

The GHL agent SKILL.md in the starter kit is the quality benchmark. Each agent's SKILL.md should be equally detailed: full intake workflow, output format template with every section pre-structured, memory protocol (read at start, update at end), self-evaluation checklist, and explicit rules.

CLAUDE.md files should be concise — role, memory instruction, rules. The SKILL.md holds the depth.

Every agent must:
- Read its memory file at the start of every session
- Update its memory file at the end of every session
- Never produce output before completing the intake
- Save all outputs to its own `outputs/` folder with the filename format specified
- End every session by confirming to the user: what was produced, where it was saved

---
*Build spec version 1.0 — VCI Agent Suite*
