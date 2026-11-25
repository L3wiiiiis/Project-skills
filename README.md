# Project-skills

Projects and skills I've created. Skills are instruction files that teach Claude (and other AI agents) how to do a particular kind of task well.

## Skills

### [personal-tutor](personal-tutor/SKILL.md)

Turns an AI assistant into a patient tutor for any subject, teaching from reliable sources. Instead of making things up or dumping information, it:

- **asks one quick setup question** with sensible defaults (say *go* to skip it), then starts teaching straight away
- **sources the material** from your own course materials first, then open textbooks, official documentation, scholarly encyclopedias and government sites, and cites them
- **shows a short plan** of 3–7 milestones (say *change* any time to adjust)
- **teaches one idea per turn**, and asks you to guess before revealing
- **moves on only when you can actually do it**, not just when it's been explained
- **tracks progress** with a status line you can paste next time to continue

**Five modes:** **Learn** (step by step), **Lecture** (structured, sourced lessons one section at a time, with optional animated diagrams or short narrated videos), **Exam** (short and direct), **Practice** (you try first), and **Continue** (pick up where you left off). It also has playbooks for law, health, writing and editing, coding, maths, philosophy, and fact-heavy subjects.

**It will never** invent books, cases, quotes or statistics, or reproduce copyrighted text. When it can't verify something, it says so.

**Try saying**
- `teach me recursion`
- `lecture me on supply and demand`
- `I have a statistics exam on Friday, help me revise hypothesis testing`
- `quiz me on the French Revolution`
- `continue Python` (then paste your last 📍 status line if asked)

**Example**

> **You:** teach me recursion
> **Tutor:** Quick setup — answer any of these, or just say *go*: 1. Focus: (a) how recursion works (b) writing recursive functions (c) recursion on trees  2. Level [beginner]  3. Time [15 min]  4. It's for [curiosity]
> **You:** c, exam, an hour
> **Tutor:** Here's the plan… *(and the first lesson starts in the same reply)*
> …
> 📍 Recursion | Goal: solve tree problems for my exam | Milestone 2/4: base cases | Locked: ① call stack | Weak: return values | Next: tree traversal

## Installing a skill

**Claude app (web or desktop):** download the skill's folder as a ZIP, then upload it under **Settings → Capabilities → Skills**.

**Claude Code:** copy the folder into your skills directory:

```
git clone https://github.com/L3wiiiiis/Project-skills.git
cp -r Project-skills/personal-tutor ~/.claude/skills/
```

On Windows, copy the `personal-tutor` folder into `%USERPROFILE%\.claude\skills\`.

**Other agents:** most agents that support `SKILL.md` files will load it from their skills folder. Check your agent's docs.

## What works where

| Feature | Claude app | Claude Code / other agents |
|---|---|---|
| Tutoring, modes, mastery checks | ✅ | ✅ |
| Sourced teaching with citations | ✅ (with web search on) | ✅ if the agent has web search; otherwise general knowledge, clearly flagged |
| Resume from past chats automatically | ✅ (if chat search or memory is on) | Paste your last 📍 status line |
| Animated diagrams / short videos | ✅ (where the app supports them) | Where the agent can run code or render video; otherwise static diagrams |
| Quiz widget | ✅ | Plain-text quiz |
| Saved notes / cheat sheet as a document | ✅ | Written in the chat |

## Limits

- It can't read most books. It teaches from open sources and your own materials, and recommends books (checked to exist) for further reading.
- It's a study aid, not legal, medical or financial advice.

## Testing

`personal-tutor/tests/test-prompts.md` lists prompts to check the skill behaves as intended. If you find a case where it doesn't, please open an issue with the prompt and what happened.

## Credits and licence

`personal-tutor` builds on ideas from [learn-x by dimayip](https://github.com/dimayip/learn-x) (MIT).

Released under the [MIT Licence](LICENSE): you're free to use, change and share it, as long as you keep the licence notice.
