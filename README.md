# Capable drug-discovery environments

Agent environments built from Capable's own laboratory data: 9 environments, 666 tasks.
Every task is one episode with one reward, so the same tasks serve as an evaluation (average the rewards)
or as a reinforcement-learning environment. Tasks are packaged for [Harbor](https://harborframework.com).

This repository describes the environments. The tasks themselves are built from unpublished structures and
measurements, so they stay on Capable's infrastructure and are run there.

## Environments

### Design campaigns

| Environment | Tasks | Interaction | What the agent does |
|---|---|---|---|
| [Design campaign over several rounds](environments/design-campaign-rounds.md) | 6 | interactive | Run a retrospective design campaign over one generation of a peptide programme: pick four compounds a round for three rounds, seeing what each pick measured before choosing the next. |
| [Design-round ranking: peptides](environments/design-round-ranking-peptides.md) | 52 | single answer | A design round from one of our peptide campaigns: rank the round's candidates by the potency they turned out to have. |
| [Design-round ranking: short modified peptides](environments/design-round-ranking-short-peptides.md) | 16 | single answer | A real design round from one of our programmes: rank the round's candidates by the potency they turned out to have. |

### Lab data analysis

| Environment | Tasks | Interaction | What the agent does |
|---|---|---|---|
| [Mouse activity analysis](environments/mouse-activity-analysis.md) | 13 | single answer | Reproduce a mouse study's hourly activity analysis from raw 24/7 home-cage video tracking. |
| [Lab notation to chemical structure](environments/notation-to-structure.md) | 449 | single answer | Convert a registered peptide written in the lab's shorthand into its exact chemical structure. |
| [Raw assay curve fitting](environments/raw-assay-curve-fitting.md) | 24 | single answer | Turn one cell assay's raw plate-reader export into compound potencies. |

### Potency prediction

| Environment | Tasks | Interaction | What the agent does |
|---|---|---|---|
| [Build a potency model](environments/build-a-potency-model.md) | 6 | single answer | A long-horizon modelling task: train any model on measured potencies, then rank compounds it has not seen. |
| [Held-out potency regression](environments/held-out-potency-regression.md) | 70 | single answer | Predict the measured potency of a peptide from one of our programmes, held out from every related compound. |
| [Pairwise potency in context](environments/pairwise-potency-in-context.md) | 30 | single answer | Two analogues from one of our peptide programmes, measured side by side in the same assay: say which is more potent and by how much. |

## How an evaluation runs

1. You send Capable an agent: a Harbor agent name and model, or a package exposing a Harbor agent class.
2. Capable runs it on every task, each in its own sandbox, on Capable's compute.
3. You receive the reward for every task and the aggregate for every environment.

Task inputs and transcripts stay with Capable. The model acting as the agent reads each task's inputs
during its run.

## Isolation

- The agent works as an unprivileged user and can reach only its model provider and the Python package
  index (plus the episode service, for interactive tasks).
- A single-answer task is graded in a separate verifier sandbox that receives only the answer file.
- An interactive task's hidden results live in a separate episode service the agent cannot read. Its
  score is final once taken: the service then refuses further actions.
- The grader runs in isolated mode, so nothing the agent writes can replace it.

## Interactive tasks

The agent acts only through the episode service: `POST http://oracle:8000/act` with one action as JSON returns
the next state, whether the episode is over and any error; `GET http://oracle:8000/observation` returns the
current state.
