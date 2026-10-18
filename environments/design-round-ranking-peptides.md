# Design-round ranking: peptides

A design round from one of our peptide campaigns: rank the round's candidates by the potency they turned out to have.

## What the agent gets

The parent peptide, every analogue measured before the round with its potency, and the round's candidates as sequences in lab notation. A round is every compound first measured on the same day.

## What the agent returns

A ranking of every candidate, most potent first.

## Grading

Spearman correlation between the ranking and the potency the team measured, from -1 to 1. The answer file is graded in a separate verifier sandbox; the hidden answer never enters the agent's sandbox.

## At a glance

|  |  |
|---|---|
| Family | Design campaigns |
| Tasks | 52 |
| Interaction | single answer |
| Agent budget | 30 min, 2 CPUs, 4 GB |
| Network | api.anthropic.com, api.openai.com, openrouter.ai, pypi.org, files.pythonhosted.org |
| Release | `d4e794ac73e4` |
