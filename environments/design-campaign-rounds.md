# Design campaign over several rounds

Run a retrospective design campaign over one generation of a peptide programme: pick four compounds a round for three rounds, seeing what each pick measured before choosing the next.

## What the agent gets

Earlier generations with their measured potency, and the current generation's compounds as a pool of candidates with sequences and structures.

## What the agent returns

Four candidates per round, sent to the episode service; each round reveals the picks' measured potency.

## Grading

How close the best pick comes to the pool's most potent compound, as a fraction of the pool's potency range, from 0 to 1. The agent acts through the episode service (`http://oracle:8000`), which holds the hidden results and scores the episode when it ends.

## At a glance

|  |  |
|---|---|
| Family | Design campaigns |
| Tasks | 6 |
| Interaction | interactive |
| Agent budget | 30 min, 2 CPUs, 4 GB |
| Network | api.anthropic.com, api.openai.com, openrouter.ai, pypi.org, files.pythonhosted.org, the episode service |
| Release | `c4ac5073e5ca` |
