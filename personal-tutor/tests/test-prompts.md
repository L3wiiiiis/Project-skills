# Test prompts for personal-tutor

Run each prompt in a fresh chat with the skill installed. Tick it off only if the expected behaviour happens.

| # | Prompt | Expected behaviour |
|---|---|---|
| 1 | `teach me recursion` | Learn mode. Sends **one** setup message (focus options, level, time, purpose, each with a default, and "say *go*"). Teaches nothing yet. |
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
| 13 | `lecture me on supply and demand`, then answer the setup | Lecture mode. One setup message, then the plan **and** the first section in the same reply (≤ ~600 words, key points, sources), ending with a check question and "say *next*". Doesn't wait for plan approval. |
| 14 | During Lecture mode, say `next` three times quickly | Gives one section per reply, never several at once. |
| 15 | Upload lecture slides and say `teach me this` | Teaches from the slides first, using their terms; only adds outside sources to fill gaps, and says where they differ. |
| 16 | `lecture me on the water cycle` | The visuals choice (animated diagrams / short narrated video / none) is a line **inside** the single setup message, not a separate question. Only offers options the environment can make. |
| 17 | Choose animated diagrams, then continue the water cycle lecture | Adds an animated diagram only to sections with a process or change; labels are correct and match the cited sources. No animation for definition-only sections. |
| 18 | `lecture me on the brain`, then reply only `go` | Starts teaching immediately with all defaults, says which focus it picked, and asks **no** further setup question. |
| 19 | `teach me economics`, then reply only `b, 5 min` | Uses focus (b) and 5 minutes, fills the rest with defaults, and starts. One-line plan; no follow-up question. |
| 20 | Choose a short video in Lecture mode | The video is narrated if a voice is available (otherwise it says up front the video will be silent), has on-screen text carrying the full meaning, marks simplifications, shows sources on the last frame, and is about 60–90 seconds. |
| 21 | In Lecture mode, ask for the video before the section | Makes the video first, then gives key points with sources and a check question; doesn't insist on the text section first. |

## Results

| Date | Environment (Claude app / Claude Code / other) | Passed | Notes |
|---|---|---|---|
| 25 Nov 2026 | Claude app | 16 (partly), 21 | Lecture test on the brain (prefrontal cortex). Found: video had no sound (fixed, now test 20); 3 setup questions used half of a 5-minute session (fixed with one setup message, tests 18–19); narrated video ran 80 s, over the 60 s limit (limit now 60–90 s). |
