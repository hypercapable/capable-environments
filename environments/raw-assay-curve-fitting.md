# Raw assay curve fitting

Turn one cell assay's raw plate-reader export into compound potencies.

## What the agent gets

The plate reader's raw export, the plate map and the written assay protocol.

## What the agent returns

A pEC50 for each compound on the plates.

## Grading

The share of key compounds reported within 0.3 log units. The key holds compounds whose curves passed the run's own quality control (R² of at least 0.9) and whose value agrees with our registry within 0.3 log units. The answer file is graded in a separate verifier sandbox; the hidden answer never enters the agent's sandbox.

## At a glance

|  |  |
|---|---|
| Family | Lab data analysis |
| Tasks | 24 |
| Interaction | single answer |
| Agent budget | 60 min, 2 CPUs, 4 GB |
| Network | api.anthropic.com, api.openai.com, openrouter.ai, pypi.org, files.pythonhosted.org |
| Release | `439645f6a765` |
