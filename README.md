# think-first

An agent skill that keeps you doing the thinking. Turn it on and your AI
stops taking over tasks you hand it blind: it pauses, asks you the one
question that is yours to answer, gives you what you need to answer it,
and then works through the task with you.

It works with any agent that reads [Agent Skills](https://agentskills.io)
(`SKILL.md`): Claude Code, Codex, OpenCode and others.

## What it looks like

> **You:** Write a SQL query for churned users.
>
> **AI:** What counts as churned is your call, and it changes the answer.
> The usual choices are: no activity for 30 days (catches drift early,
> flags people on holiday), a cancelled subscription (exact, but misses
> people who just stop), or no payment in the last billing cycle (fits
> paid products). Which fits what you're measuring?

Send the same request with your thinking in it, "Churned = no login in 30
days, query the `events` table", and it just writes the query.

## Where the line is

The AI judges only what your request shows, never who you are. It pauses
when both of these hold:

1. **The request is blind.** It shows none of your own thinking: no
   attempt, guess, definition, constraint or position.
2. **It holds a judgment.** There is a decision, definition, trade-off or
   step of reasoning in it, not only mechanical work.

The AI gives you information freely: facts, explanations, options and
their trade-offs, critique, hints, and all mechanical work. Judgment stays
with you: definitions, positions, choices, conclusions.

Each pause is one question. It never refuses: say "just do it" and it
does the work, telling you in one line which decision it made for you.

[`SKILL.md`](skills/think-first/SKILL.md) has the full set of examples.

## Install

With the [skills](https://skills.sh) CLI, for any supported agent:

```bash
npx skills add brianjmeier/think-first
```

Or by hand in Claude Code, for all your projects, from a clone of this
repo:

```bash
mkdir -p ~/.claude/skills/think-first && cp skills/think-first/SKILL.md ~/.claude/skills/think-first/
```

Other agents: copy `skills/think-first/` into your agent's skills folder.

## Use

Turn it on in a conversation with `/think-first`, or say "make me think"
or "teach me instead of doing it for me". It stays on until you say
"stop think-first" or "normal mode".

It is opt-in on purpose. You decide when you want to learn and when you
just need something done.

## Why

Handing a task to an AI is *cognitive offloading*: using something outside
your head to reduce the mental effort a task takes. Offloading mechanical
work is healthy. The harm comes from offloading a skill you need, because
you then can't check what comes back.

In a randomized trial with about 1,000 high-school students, those given
plain GPT-4 scored 48% higher in practice and 17% lower on the exam they
then took alone. A version that only gave hints prevented the harm but
taught nothing extra. An AI tutor that had students take each step and
gave feedback did teach: Harvard students using one learned about twice as
much as in an active-learning class.

So this skill does more than hold back answers. You produce the thinking,
and the AI helps you check and improve it. [docs/research.md](docs/research.md)
has the studies and their limits.

## Testing

[evals/cases.md](evals/cases.md) lists the requests used to check the
skill, each with the expected first move, and the latest results.

## License

[MIT](LICENSE)
