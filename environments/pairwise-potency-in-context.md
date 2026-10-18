# Pairwise potency in context

Two analogues from one of our peptide programmes, measured side by side in the same assay: say which is more potent and by how much.

## What the agent gets

Both peptides' sequences and structures, the assay they were measured in, and reference compounds from the programme's earlier design generations with their measured potency.

## What the agent returns

Which compound is more potent (A or B) and a five-level rating of the potency ratio: B over 30-fold more potent, B at least 3-fold more potent, within 3-fold, A at least 3-fold more potent, A over 30-fold more potent.

## Grading

1 when the more potent compound is named correctly, otherwise 0; the rating's accuracy is reported alongside. The answer file is graded in a separate verifier sandbox; the hidden answer never enters the agent's sandbox.

## At a glance

|  |  |
|---|---|
| Family | Potency prediction |
| Tasks | 30 |
| Interaction | single answer |
| Agent budget | 30 min, 2 CPUs, 4 GB |
| Network | api.anthropic.com, api.openai.com, openrouter.ai, pypi.org, files.pythonhosted.org |
| Release | `9acc90f2e946` |
