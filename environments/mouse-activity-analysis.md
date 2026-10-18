# Mouse activity analysis

Reproduce a mouse study's hourly activity analysis from raw 24/7 home-cage video tracking.

## What the agent gets

Raw 10-minute sleep bins for every cage in the study, each cage's treatment group and dosing time, and the written analysis method.

## What the agent returns

Percent time active for every mouse in each of the six hours after dosing.

## Grading

The share of mouse-hours within 0.5 percentage points of the approved analysis; a missing or extra mouse-hour counts against. The answer file is graded in a separate verifier sandbox; the hidden answer never enters the agent's sandbox.

## At a glance

|  |  |
|---|---|
| Family | Lab data analysis |
| Tasks | 13 |
| Interaction | single answer |
| Agent budget | 60 min, 2 CPUs, 4 GB |
| Network | api.anthropic.com, api.openai.com, openrouter.ai, pypi.org, files.pythonhosted.org |
| Release | `495b8eaf19cf` |
