# Test prompts for personal-tutor

Run each prompt in a fresh chat with the skill installed. Tick it off only if the expected behaviour happens.

| # | Prompt | Expected behaviour |
|---|---|---|
| 1 | `teach me recursion` | Learn mode. Sends **one** short setup message (about 3 lines: focus options, level, time, each with a default, and "say *go*"). Teaches nothing yet. |
| 2 | `what does HTTP 404 mean?` | Does **not** start a session. Answers directly, then offers one line: "Want to learn this properly?…" |
| 3 | `quiz me on photosynthesis, my exam is tomorrow` | Exam/Practice mode. No onboarding. Short, direct questions; waits for each answer. |
| 4 | Start a session, then say `just tell me the answer` three times | 1st: asks for a guess. 2nd: 80% answer with a blank. 3rd: full answer, then a transfer question. |
| 5 | `continue Spanish` (no past chats, no memory) | Says it can't find past progress and asks for the last status line or milestone. Does **not** restart diagnosis or pretend to remember. |
| 6 | Paste an assignment question and say `help me with this` | Asks once whether AI help is allowed for this assessment. |
| 7 | `teach me contract law, I've got 20 minutes` | Asks where the learner is (jurisdiction). Plan cut to one concept + one application. Uses the short-session mastery rule. |
| 8 | During a session, give a confidently wrong answer | Says clearly it's wrong and why. Doesn't soften it into agreement. |
| 9 | Finish a session | Prints the 📍 status line, offers a quiz and artifact choices, and tells the learner to copy the status line. Only claims to save if it actually can. The artifact ends with a **Sources** list. |
| 10 | `teach me how vaccines work` (web search on) | Searches before teaching. Cites reliable sources (e.g. WHO, national health agency, open textbook) as it goes. Lists them in the plan's "Main sources". |
| 11 | `teach me how vaccines work` (web search off) | Says once it can't look things up and is teaching from general knowledge. Marks uncertain claims. Doesn't pretend to cite. |
| 12 | `what's the best book to learn economics? read me chapter 1` | Recommends real books it has checked exist. Refuses to reproduce chapter text; offers to teach the ideas instead. |
| 13 | `lecture me on supply and demand`, then answer the setup with 15 min | Lecture mode. One setup message, then the plan **and** the first section in the same reply (≤ ~600 words, key points, sources), ending with a check question and "say *next*". Doesn't wait for plan approval. |
| 14 | During Lecture mode, say `next` three times quickly | Gives one section per reply, never several at once. |
| 15 | Upload lecture slides and say `teach me this` | Teaches from the slides first, using their terms; only adds outside sources to fill gaps, and says where they differ. |
| 16 | `lecture me on the water cycle` | The visuals choice (animated diagrams / short narrated video / none) is a line **inside** the single setup message, not a separate question. Only offers options the environment can make. |
| 17 | Choose animated diagrams, then continue the water cycle lecture | Adds an animated diagram only to sections with a process or change; labels are correct and match the cited sources. No animation for definition-only sections. |
| 18 | `lecture me on the brain`, then reply only `go` | Starts teaching immediately with all defaults, says which focus it picked, and asks **no** further setup question. |
| 19 | `teach me economics`, then reply only `b, 5 min` | Uses focus (b) and 5 minutes, fills the rest with defaults, and starts. One-line plan; no follow-up question. |
| 20 | Choose a short video in Lecture mode | The video is narrated if a voice is available (otherwise it says up front the video will be silent), has on-screen text carrying the full meaning, marks simplifications, shows sources on the last frame, and is about 60–90 seconds. |
| 21 | In Lecture mode, ask for the video before the section | Makes the video first, then gives key points with sources and a check question; doesn't insist on the text section first. |
| 22 | `lecture me on economics`, then reply `30+ min` | Shows a topic menu (4–8 topics with times and sources) and **waits**. Says *go* means all in order, and that topics can be picked, skipped, reordered or added. |
| 23 | At the topic menu, reply `just 3 and 5, and add inflation` | Teaches only topics 3 and 5 plus inflation, in that order, starting straight away. No further question (at most a one-line note if a missing earlier topic is needed). |

## Results

All tests so far were run in the **Claude app** (web/desktop) on 25 Nov 2026, by the skill's author. Tests not listed here have **not been run yet**.

**Key:** ✅ pass · ❌ fail · ⚠️ partial · ⏳ not run yet

### Test log

| # | Date | Version tested | Test | Result | What happened |
|---|---|---|---|---|---|
| R1 | 25 Nov 2026 | v2 (first public version) | General use after installing | ✅ | Author tried it in a new chat and was happy with it. Specific prompts weren't recorded. |
| R2 | 25 Nov 2026 | v3 (Lecture + animations) | `lecture me on the water cycle`, switched by the learner to "the brain in 5 minutes" | ✅ | Coped with the topic change and narrowed a huge topic ("the brain") to one idea that fits 5 minutes. |
| R3 | 25 Nov 2026 | v3 | Setup questions before teaching (5-minute session) | ❌ | Asked **3 separate questions** (goal, which part of the brain, visuals) before teaching anything, which used about half the session. |
| R4 | 25 Nov 2026 | v3 | Visuals choice offered (test 16) | ⚠️ | Offered diagrams / video / none and only options the app can make, but as a separate question (later changed to a line inside the setup message). |
| R5 | 25 Nov 2026 | v3 | Sourced teaching (test 10) | ✅ | Searched before teaching, used reliable sources (open psychology textbooks, NCBI Bookshelf, peer-reviewed reviews) and cited them. |
| R6 | 25 Nov 2026 | v3 | One concept for a short session | ✅ | Plan cut to one concept (prefrontal cortex and behaviour, via the Phineas Gage case) plus one check question. |
| R7 | 25 Nov 2026 | v3 | Learner asks for the video first (test 21) | ⚠️ | Made the video as asked, but the skill at the time said "section first, then video", so it broke its own rule. Rule changed so the learner's choice wins. |
| R8 | 25 Nov 2026 | v3 | Video built with code, accurate labels | ✅ | Code-drawn diagram, labels correct, simplifications marked on screen, sources on the last frame. First drafts had overlapping text and wrong lobe boundaries; caught by checking frames before rendering. |
| R9 | 25 Nov 2026 | v3 | Video has sound | ❌ | First video was **silent**; the skill never mentioned narration. Fixed in the session with an open-source voice (Kokoro). |
| R10 | 25 Nov 2026 | v3 | Video length (≤ 60 s rule) | ❌ | Narrated version ran **80 s**, because speech is slower than reading. Limit changed to 60–90 s, with narration written to fit. |
| R11 | 25 Nov 2026 | v3 | Check question after the video | ✅ | Ended with key points, sources and one application question. |
| R12 | 25 Nov 2026 | v5 (one-message setup) | `teach me economics` (test 1) | ✅ | One setup message with focus options, level, time and purpose, each with a default and "say *go*". Teaches nothing yet. |
| R13 | 25 Nov 2026 | v5 | Setup length (≤ 3 lines, 4th only when it matters) | ⚠️ | Used 4 lines; the 4th (purpose) is allowed because it changes depth for economics. Within the 5-line limit. |
| R14 | 25 Nov 2026 | v5 | No default country | ⚠️ | Chose Australian examples. That came from the author's own Claude account context, not the skill, so it's fine for the author. Needs testing from another person's account to confirm the skill stays neutral. |
| R15 | — | v5 | Topic menu for 30+ min (tests 22–23) | ⏳ | Not run yet. |
| R16 | — | — | Tests 2–9, 11–15, 17–20 | ⏳ | Not run yet. |
| R17 | — | — | Claude Code / other agents | ⏳ | Not tested outside the Claude app yet. |

### Fixes made because of these results

| Problem found | Fix | Version |
|---|---|---|
| Skill was personal (author's name, Australian law and style defaults) and relied on tools many users lack | Made general; asks country/style only when it matters; fallback for every tool | v2 |
| No sources; risk of invented facts | Step 2 "Source the material", trusted-sources guide, no invented books or quotes, copyright limits | v2 |
| No way to just listen or read | Lecture mode, one section per message | v2 |
| Mastery rule too slow for short sessions | Lighter rule under 30 min and in Exam mode | v2 |
| No visuals | Optional animated diagrams or short videos, code-built | v3 |
| Silent video (R9) | Narration via text-to-speech, or warn first and use full on-screen text | v4 |
| No captions | On-screen text carries the full meaning | v4 |
| Video too long (R10) | 60–90 s, narration written to fit | v4 |
| Video-first request broke a rule (R7) | Learner's choice wins; video + key points + check question counts as the section | v4 |
| Simplified diagrams could mislead | Mark simplifications on screen; sources on the last frame | v4 |
| Too many setup questions (R3) | One setup message with defaults; any reply starts the lesson; never a second setup question | v4 |
| Setup message could feel like a form | Trimmed to ~3 lines, extra lines only when they matter | v5 |
| Long sessions risk a wrong plan | Topic menu for 30+ min: pick, skip, reorder or add any topic; *go* = all | v5 |

### Versions

| Version | What changed |
|---|---|
| v1 | Personal version for the author only (not published) |
| v2 | First public version: general, sourced teaching, Lecture mode, tool fallbacks, README, MIT licence |
| v3 | Animated diagrams / short videos offered in Lecture mode |
| v4 | Narrated, captioned videos; one-message setup for impatient learners |
| v5 | Shorter setup; topic menu for 30+ minute sessions (current) |
