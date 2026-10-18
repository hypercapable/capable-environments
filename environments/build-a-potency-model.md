# Build a potency model

A long-horizon modelling task: train any model on measured potencies, then rank compounds it has not seen.

## What the agent gets

train.csv with structures and measured potency, and test.csv with held-out structures. One task comes from one of our peptide programmes (held out by chemical family); five come from public receptor data (held out by source series).

## What the agent returns

A ranking of every test compound, most potent first.

## Grading

Spearman correlation between the ranking and measured potency, from -1 to 1. The answer file is graded in a separate verifier sandbox; the hidden answer never enters the agent's sandbox.

## At a glance

|  |  |
|---|---|
| Family | Potency prediction |
| Tasks | 6 |
| Interaction | single answer |
| Agent budget | 120 min, 4 CPUs, 8 GB |
| Network | api.anthropic.com, api.openai.com, openrouter.ai, pypi.org, files.pythonhosted.org |
| Release | `22adc38dad42` |
