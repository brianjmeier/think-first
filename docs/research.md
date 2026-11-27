# The research behind think-first

## Cognitive offloading

Risko and Gilbert define cognitive offloading as using physical action to
change the information-processing demands of a task so it takes less
mental effort: writing a list, using a calculator, searching instead of
remembering. People do it because working memory and attention are
limited, and most of the time it is the sensible choice.

- Risko, E. F., & Gilbert, S. J. (2016). Cognitive offloading. *Trends in
  Cognitive Sciences, 20*(9), 676–688.
  [Full text (UCL)](https://discovery.ucl.ac.uk/1508770/)

Generative AI changes what can be offloaded. Earlier tools stored
information and left the thinking to you. An AI can do the reasoning,
structuring, writing and judging as well.

## What the studies found

**Answers harm learning; a tutor that only hints doesn't help it either.**
A randomized trial with about 1,000 Turkish high-school students compared
plain GPT-4, a "GPT Tutor" told to give hints and never answers, and no
AI. In practice, the GPT-4 group scored 48% higher and the Tutor group
127% higher than control. On the later exam without AI, the GPT-4 group
scored 17% lower than control. The Tutor group scored about the same as
control: the harm was gone, but so was any gain. Students also
misjudged how much they had learned.

- Bastani, H., et al. (2025). Generative AI without guardrails can harm
  learning: Evidence from high school mathematics. *PNAS, 122*(26),
  e2422633122. [Article](https://www.pnas.org/doi/10.1073/pnas.2422633122)

**A tutor built on teaching practice does teach.** 194 Harvard physics
students learned one topic from an AI tutor designed around active
learning (step by step, the student does the work, with feedback) and
another in an active-learning class. Median learning gains with the tutor
were more than double, in less time. The authors caution that this was
one short-term post-test, and that synthesis-heavy topics may differ.

- Kestin, G., Miller, K., et al. (2025). AI tutoring outperforms in-class
  active learning. *Scientific Reports, 15*, 17458.
  [Article](https://www.nature.com/articles/s41598-025-97652-6)

**Trusting the AI goes with thinking less.** In a survey of 319 knowledge
workers describing 936 real tasks, more confidence in the AI went with
less critical thinking, and more confidence in their own skill went with
more. Workers often skipped critical thinking when they lacked the skill
to check the AI's output. Self-reported.

- Lee, H.-P., et al. (2025). The impact of generative AI on critical
  thinking. *CHI '25*.
  [PDF](https://www.microsoft.com/en-us/research/wp-content/uploads/2025/01/lee_2025_ai_critical_thinking_survey.pdf)

**Heavy offloading goes with weaker critical thinking.** In a 666-person
survey, AI use correlated with offloading (r = 0.72) and negatively with
critical thinking (r = −0.68), with offloading carrying much of the link.
Moderate use showed no significant effect. Correlational.

- Gerlich, M. (2025). AI tools in society: Impacts on cognitive
  offloading and the future of critical thinking. *Societies.*
  [Summary](https://www.psypost.org/ai-tools-may-weaken-critical-thinking-skills-by-encouraging-cognitive-offloading-study-suggests/)

**Order matters.** In an EEG study of 54 people writing essays, those who
used ChatGPT showed the weakest brain connectivity, felt least ownership
and often couldn't quote their own essays. People who wrote alone first
and then used ChatGPT stayed engaged. Small, not peer reviewed, and its
methods have been criticized.

- Kosmyna, N., et al. (2025). Your brain on ChatGPT.
  [arXiv](https://arxiv.org/abs/2506.08872) ·
  [Critique](https://arxiv.org/pdf/2601.00856)

**How AI is used matters more than how much.** Structured prompting
reduced offloading and improved reasoning compared with unguided use.

- [MDPI *Data* (2025)](https://www.mdpi.com/2306-5729/10/11/172) ·
  [APA Monitor (2026)](https://www.apa.org/monitor/2026/07-08/ai-job-skills-thinking)

## How the skill follows from this

| Finding | Design choice |
|---|---|
| Harm comes from offloading a skill you need and can't check | Pause only when a request is blind and holds a judgment |
| Hints alone prevented harm but taught nothing | After the pause, the person takes the step and gets feedback |
| Trust in the AI displaces checking | When the AI does decide, it names the decision so the person can check it |
| Thinking first, then using AI, kept people engaged | Ask for the person's position before drafting |
| Moderate, deliberate use showed no harm | Opt-in, one question per task, "just do it" always wins |

## Limits

Most of this evidence is short-term, and much of it is self-reported or
correlational. The two strongest studies are classroom trials, not
workplace ones. The skill applies the pattern they share; it is not a
proven intervention in its own right.
