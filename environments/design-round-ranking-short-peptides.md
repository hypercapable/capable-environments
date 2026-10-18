# Design-round ranking: short modified peptides

A real design round from one of our programmes: rank the round's candidates by the potency they turned out to have.

## What the agent gets

The parent compound, the objectives the chemists wrote down for the round, every analogue measured before the round with its potency, and the round's candidates as chemical structures only.

## What the agent returns

A ranking of every candidate, most potent first.

## Grading

Spearman correlation between the ranking and the potency the team measured, from -1 to 1. The answer file is graded in a separate verifier sandbox; the hidden answer never enters the agent's sandbox.

## At a glance

|  |  |
|---|---|
| Family | Design campaigns |
| Tasks | 16 |
| Interaction | single answer |
| Agent budget | 30 min, 2 CPUs, 4 GB |
| Network | api.anthropic.com, api.openai.com, openrouter.ai, pypi.org, files.pythonhosted.org |
| Release | `f9f231096ceb` |
