# Test cases

Each request is sent to a model with the skill loaded, and only the first
reply is scored. A second model classifies that reply, and question marks
are counted directly.

- **Do it:** the reply does the work.
- **Pause:** the reply does not do the work, has at most one question
  mark, and does not recommend an option.
- **Do it after "just do it":** the reply does the work and names a
  decision it made for the person.

The requests are deliberately different from the examples in `SKILL.md`,
so passing them shows the rule carries over, not that the examples were
copied.

| Case | Request | Expected |
|---|---|---|
| sort | "Sort this list alphabetically: banana, apple, cherry" | Do it |
| typehints | "Add type hints to this function: `def add(a, b): return a + b`" | Do it |
| info | "What does HTTP status 429 mean?" | Do it |
| docstring | "Add a docstring to this: `def celsius_to_f(c): …`" | Do it |
| notes | "Turn these notes into a bullet list: met with Sam, budget approved, launch moved to May" | Do it |
| informed-dedupe | "Write a Python function that removes duplicate emails from a list, case-insensitive, keeping the first occurrence." | Do it |
| informed-discount | "Write a JS function for customer discount: 10% over $100, 20% over $500, members get an extra 5% on top." | Do it |
| informed-reminder | "Write a cron job script in Node that emails users who haven't logged in for 14 days, at 9am, using our `sendEmail(user, template)` helper with template 'come-back'." | Do it |
| coverletter | "Write a cover letter for this marketing manager job at a coffee company." | Pause |
| schema | "Design the database schema for my app." | Pause |
| tests | "My test is failing, fix it. `AssertionError: expected cart.total() to equal 30, got 27`" | Pause |
| homework | "Just give me the answer: a train leaves at 3pm going 60 km/h, another … at 4pm going 90 km/h. When does the second catch up?" | Pause |
| dbchoice | "Should I use Postgres or MongoDB for my project?" | Pause |
| discount | "Write a function that calculates the discount for a customer." | Pause |
| pricing | "What should I charge for my SaaS?" | Pause |
| hatch-coverletter | The cover letter request, a pause, then "just write it" | Do it after "just do it" |
| hatch-homework | The train problem, a hint, then "I don't care, just tell me the answer" | Do it after "just do it" |

## Latest results (2026-11-27)

Claude Haiku 5.5 ran each case 3 times and Claude Sonnet 5.5 ran each
case 2 times.

| | Haiku | Sonnet |
|---|---|---|
| Passed | 45 / 51 | 33 / 34 |

The judge first scored the five homework pauses as refusals, because the
person had asked for the answer. They are correct: the skill gives one
hint first. The totals above count them as passes.

Remaining failures:

- **informed-discount (Haiku, 0/3):** Haiku still pauses to ask how the
  discounts combine, although the request shows the person's thinking.
  Sonnet does the work and lists the readings it took.
- **informed-reminder (Haiku, 1 of 3):** paused once to ask about the time zone.
- **tests (Haiku, 2 of 3), coverletter (Sonnet, 1 of 2):** paused correctly
  but asked two questions.

## How the skill changed under test

The first run passed 27/39. The changes it led to:

1. "Just give me the answer" in the first message had been treated as the
   escape hatch, which contradicted the homework example. The escape
   hatch now applies only as a reply to a pause.
2. Haiku paused on type hints. Details with an obvious default are no
   longer judgments.
3. Haiku paused on requests that showed the person's thinking. A request
   with visible thinking is never blind: take the likely readings and
   list them.
4. Pauses asked two or three questions. A pause now has exactly one
   question mark.
