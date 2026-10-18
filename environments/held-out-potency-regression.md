# Held-out potency regression

Predict the measured potency of a peptide from one of our programmes, held out from every related compound.

## What the agent gets

One compound's structure and the assay it was measured in. Held-out compounds share no chemical family with the programme's other compounds.

## What the agent returns

One number: the predicted potency as pEC50 (-log10 molar).

## Grading

The negative absolute error in log units for each task; Spearman correlation across all tasks. The answer file is graded in a separate verifier sandbox; the hidden answer never enters the agent's sandbox.

## At a glance

|  |  |
|---|---|
| Family | Potency prediction |
| Tasks | 70 |
| Interaction | single answer |
| Agent budget | 30 min, 2 CPUs, 4 GB |
| Network | api.anthropic.com, api.openai.com, openrouter.ai, pypi.org, files.pythonhosted.org |
| Release | `1e4d93af0f16` |
