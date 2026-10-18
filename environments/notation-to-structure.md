# Lab notation to chemical structure

Convert a registered peptide written in the lab's shorthand into its exact chemical structure.

## What the agent gets

The peptide in lab notation: D-residues, N-methylations, side-chain variants, lipidations and caps.

## What the agent returns

The structure as SMILES.

## Grading

1 when the structure matches the registered one exactly (InChIKey of the largest fragment), 0.5 when only the connectivity matches, otherwise 0. Every key structure is confirmed by a vendor certificate's mass or a reviewed reading of the chemist's drawing. The answer file is graded in a separate verifier sandbox; the hidden answer never enters the agent's sandbox.

## At a glance

|  |  |
|---|---|
| Family | Lab data analysis |
| Tasks | 449 |
| Interaction | single answer |
| Agent budget | 30 min, 2 CPUs, 4 GB |
| Network | api.anthropic.com, api.openai.com, openrouter.ai, pypi.org, files.pythonhosted.org |
| Release | `6d8c14b1584f` |
