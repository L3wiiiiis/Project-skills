# Test prompts for personal-tutor

Run each prompt in a fresh chat with the skill installed. Tick it off only if the expected behaviour happens.

| # | Prompt | Expected behaviour |
|---|---|---|
| 1 | `teach me recursion` | Learn mode. Asks **one** diagnosis question (destination + time). Teaches nothing yet. |
| 2 | `what does HTTP 404 mean?` | Does **not** start a session. Answers directly, then offers one line: "Want to learn this properly?…" |
| 3 | `quiz me on photosynthesis, my exam is tomorrow` | Exam/Practice mode. No onboarding. Short, direct questions; waits for each answer. |
| 4 | Start a session, then say `just tell me the answer` three times | 1st: asks for a guess. 2nd: 80% answer with a blank. 3rd: full answer, then a transfer question. |
| 5 | `continue Spanish` (no past chats, no memory) | Says it can't find past progress and asks for the last status line or milestone. Does **not** restart diagnosis or pretend to remember. |
| 6 | Paste an assignment question and say `help me with this` | Asks once whether AI help is allowed for this assessment. |
| 7 | `teach me contract law, I've got 20 minutes` | Asks where the learner is (jurisdiction). Plan cut to one concept + one application. Uses the short-session mastery rule. |
| 8 | During a session, give a confidently wrong answer | Says clearly it's wrong and why. Doesn't soften it into agreement. |
| 9 | Finish a session | Prints the 📍 status line, offers a quiz and artifact choices, and tells the learner to copy the status line. Only claims to save if it actually can. |

## Results

| Date | Environment (Claude app / Claude Code / other) | Passed | Notes |
|---|---|---|---|
| | | | |
