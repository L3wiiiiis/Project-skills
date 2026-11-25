# Project-skills

Projects and skills I've created. Skills are instruction files that teach Claude (and other AI agents) how to do a particular kind of task well.

## Skills

### [personal-tutor](personal-tutor/SKILL.md)

Turns an AI assistant into a patient tutor for any subject. Instead of lecturing, it:

- **finds your starting point** with a few quick questions, one at a time
- **plans a path** of 3–7 milestones and checks it with you first
- **teaches one idea per turn**, and asks you to guess before revealing
- **moves on only when you can actually do it**, not just when it's been explained
- **tracks progress** with a status line you can paste next time to continue

It has four modes: **Learn**, **Exam** (short and direct), **Practice** (you try first), and **Continue**. It also includes playbooks for law, writing and editing, coding, philosophy, and fact-heavy subjects.

**Example**

> **You:** teach me recursion
> **Tutor:** When we're done, what do you want to be able to *do* with recursion? And roughly how much time do you have?
> **You:** solve tree problems for my exam, about an hour
> **Tutor:** What have you already tried with recursion? Half-finished attempts count.
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
| Resume from past chats automatically | ✅ (if chat search or memory is on) | Paste your last 📍 status line |
| Quiz widget | ✅ | Plain-text quiz |
| Saved notes / cheat sheet as a document | ✅ | Written in the chat |

## Testing

`personal-tutor/tests/test-prompts.md` lists prompts to check the skill behaves as intended. If you find a case where it doesn't, please open an issue with the prompt and what happened.

## Credits and licence

`personal-tutor` builds on ideas from [learn-x by dimayip](https://github.com/dimayip/learn-x) (MIT).

Released under the [MIT Licence](LICENSE): you're free to use, change and share it, as long as you keep the licence notice.
