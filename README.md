# AutoBio

A long-term autobiography project powered by daily AI-driven prompts. Questions are drawn from a curated pool, asked via Telegram, and answers are logged into a structured life-story file over time.

---

## Repository Contents

| File | Description |
|------|-------------|
| `questions_pool.md` | Pool of autobiography questions organized by life period (Elementary, Middle School, High School, College, Early Adulthood, Mid-Adulthood, Current Life, Trauma, Self-Discovery). Questions are removed after being asked. |
| `questions_log.md` | **Private** — the live answer log. Contains dated, categorized Q&A entries. Excluded from GitHub via `.gitignore`. |
| `questions_log.md.starter` | Empty starter template showing the expected log format. Safe to share publicly. |
| `.gitignore` | Excludes `questions_log.md` (the private answer file) from version control. |
| `README.md` | This file. |

---

## How It Works

### 1. Daily Question Selection (Cron — 8:15 AM ET)
- An automated cron job runs daily at 8:15 AM Eastern.
- It reads `questions_pool.md` and **randomly selects 2 questions**.
- Questions are chosen from **different categories** when possible (e.g., one from Middle School, one from Current Life).

### 2. Delivery
- The two questions are sent to the user via Telegram in a conversational tone.

### 3. Logging
- Immediately after selection, a new dated entry is **appended** to `questions_log.md` in this format:

```markdown
## YYYY-MM-DD

### [Category Name 1]
- Q: [Question text]
- A: Awaiting answer

### [Category Name 2]
- Q: [Question text]
- A: Awaiting answer
```

- When the user replies with answers, the `Awaiting answer` placeholder is replaced with their **exact words** — no edits, no rewording.

### 4. Pool Maintenance
- After questions are selected and logged, they are **removed from `questions_pool.md`** so they are never asked again.
- The pool shrinks over time as the autobiography grows.

### 5. Long-Term Goal
- Over weeks and months, `questions_log.md` accumulates into a rich, categorized life-story transcript.
- This log can later be pulled together into a full autobiography narrative.

---

## Rules

1. **Random selection** — questions must be truly random, not sequential from the top of the pool.
2. **Different categories** — pick from different life-period sections when possible.
3. **Remove after asking** — once a question is selected, delete it from `questions_pool.md`.
4. **Log immediately** — append the Q&A block to `questions_log.md` right after asking, even before the answer arrives.
5. **Exact answers** — when the user responds, log their words verbatim. No paraphrasing, no cleanup.
6. **Never share the answer log** — `questions_log.md` is private. It must stay in `.gitignore` and never be committed to a public repo.
7. **Append only** — never overwrite or delete previous entries in `questions_log.md`.

---

## Privacy

- `questions_log.md` contains personal life stories and is **never** pushed to GitHub.
- Only the question pool, starter template, and this README are public.
- If forking or sharing this project, ensure `.gitignore` rules are intact before pushing.
