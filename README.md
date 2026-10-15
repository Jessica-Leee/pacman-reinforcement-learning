# Pacman Reinforcement Learning

An archive of UC Berkeley CS 188 coursework exploring planning and reinforcement learning in Gridworld and Pacman.

## Implemented methods

- **Batch value iteration:** compute a value function from a known Markov decision process, then derive action values and a greedy policy.
- **Prioritized sweeping:** focus value updates on states with larger Bellman errors, using predecessor sets and a priority queue. This is the course extra-credit component.
- **Tabular Q-learning:** learn action values from sampled transitions with epsilon-greedy exploration.
- **Approximate Q-learning:** represent action values as a weighted sum of features and update weights from temporal-difference errors.
- **Policy analysis:** compare how the discount factor, transition noise, and living reward change an agent's behavior.

The three assignment files are the recovered final Gradescope submission, preserved without changes to their solution logic. They include the required value-iteration, Q-learning, and approximate Q-learning methods, policy-analysis answers, and the optional prioritized-sweeping implementation.

## Architecture

| File | Role |
| --- | --- |
| `valueIterationAgents.py` | Model-based planning with batch value iteration, prioritized sweeping, and policy extraction. |
| `qlearningAgents.py` | Tabular and approximate Q-learning, epsilon-greedy action selection, and Pacman agent configuration. |
| `analysis.py` | Parameters for the policy-analysis questions. |
| `mdp.py`, `learningAgents.py` | Course-provided interfaces for MDPs and value/learning agents. |
| `gridworld.py`, `pacman.py`, `game.py` | Course-provided environments and runtime. |
| `featureExtractors.py` | Course-provided feature extractors for approximate agents. |
| `autograder.py`, `reinforcementTestClasses.py`, `test_cases/` | Course-provided local checks and test fixtures. |

The environment provides either an MDP model to a planning agent or sampled transitions to a learning agent. Planning applies Bellman backups over the model; Q-learning updates state-action estimates from experience. Both expose policies through the course agent interfaces.

## Local setup

Use Python 3 from this directory. Source inspection found no third-party Python package requirements for the local runtime and headless checks; no `pip install` step is required. Tkinter is used by graphical displays and may depend on the Python distribution. It is not needed for the commands below.

The verification used **Python 3.13.7**. The repository includes the course environments, layouts, and local test fixtures, so no dataset download, API key, or Gradescope access is required for these headless examples.

```sh
python3 autograder.py --no-graphics
```

To run a text-only Gridworld example:

```sh
python3 gridworld.py -t -a value -i 100 -k 1
```

These commands use the included local course harness and do not submit anything to Gradescope.

## Validation

The final submission was checked with **Python 3.13.7** and the included course harness:

- All 28 Python source files passed syntax compilation.
- `python3 autograder.py --no-graphics` passed all nine question groups: **25/25 regular points plus 1 extra-credit point**, reported as **26/25**.
- The Pacman Q-learning check won 100/100 evaluation games under the harness's fixed-seed configuration.

These are local harness results, not a new Gradescope grade or a claim about unseen tests. The original `grading.py` emits a non-fatal string-escape `SyntaxWarning` on Python 3.13; the course file is preserved unchanged. No GUI was opened. See [VALIDATION.md](VALIDATION.md) for the score breakdown.

These results were recorded on **October 14, 2026** and were not rerun for this documentation refresh. The 100/100 wins belong to that fixed-seed evaluation, not a general win-rate estimate. The nine question groups and their points are detailed in the [validation record](VALIDATION.md).

## Coursework provenance and access

This is CS 188 Project 3, built on the [UC Berkeley Pacman AI projects](http://ai.berkeley.edu). The framework, environments, interfaces, tests, and autograder are course-provided; the project code includes student implementations in the designated assignment files.

The original notices credit John DeNero and Dan Klein for the core projects and autograders, with student-side autograding added by Brad Miller, Nick Hay, and Pieter Abbeel. Original licensing and attribution notices are retained in the source files.

The source notices allow educational use and extension subject to retaining attribution and not distributing or publishing solutions. Original notices are preserved. Repository visibility does not grant additional open-source licensing or redistribution permission.
