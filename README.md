# The Back Room — No-Limit Hold’em Engine

A browser-based No-Limit Texas Hold’em game built alongside a Python notebook and a technical report. The project uses poker as a practical setting to explore probability, simulation, hand evaluation, state-based systems, and decision-making with incomplete information.

## Project overview

The engine supports starting tables with 4–8 players and models the progression of a hand from the deal and betting rounds through showdown and pot settlement. The project is organized into three complementary parts: an interactive game, a Python implementation of selected algorithms, and a report explaining the underlying mathematics.

## Quantitative methods explored

- **Probability and combinatorics:** poker hand frequencies, card removal, pot odds, and expected value.
- **Simulation and equity estimation:** Monte Carlo rollouts, standard-error estimates, range-conditioned equity, and exact enumeration for selected river and turn cases.
- **Algorithm design:** compact card encodings, hand-ranking scores, bitmasks, lookup tables, and comparisons between direct and optimized evaluators.
- **State and accounting logic:** betting-round progression, legal actions, short all-ins, uncalled-bet refunds, side-pot construction, and showdown settlement.
- **Decision models:** preflop hand-strength heuristics, strategy lookup tables, tournament Independent Chip Model (ICM), and a simplified Counterfactual Regret Minimization (CFR) demonstration.
- **Opponent modelling:** Beta-Binomial updates for observed tendencies and post-hand review based on expected value rather than only the realised outcome.

These methods are implemented and discussed at different levels across the game, notebook, and report. The strategy components are educational models and heuristics, not a claim of a complete, fully solved game-theoretic strategy.

## Repository contents

### `index.html` — Interactive game

The webpage provides the playable interface. It includes configurable 4–8 player starting tables, player and stack settings, AI difficulty controls, betting actions, hand-ranking and rules references, and panels displaying quantitative decision information and opponent reads.

**How to use it:** open `index.html` in a modern browser. No Python environment or build step is needed for the browser game. To host it as a webpage with GitHub Pages, keep the file named `index.html` in the published root (or the configured publishing folder).

### `no_limit_holdem_engine_algorithms.ipynb` — Python notebook

The notebook presents Python implementations and annotated explanations of the main algorithms. It includes helpers for expected value and pot odds, card encoding and shuffling, hand evaluation, Monte Carlo and exact equity calculations, betting and pot-settlement logic, decision-model examples, Bayesian updates, and invariant checks with worked examples.

**How to use it:** open the notebook in Jupyter Notebook/JupyterLab or Google Colab and run cells in order. The notebook is a companion for studying the calculations; it is not required to run the HTML game.

### `algorithms_of_a_no_limit_holdem_engine.pdf` — Technical report

The report, *Algorithms and Processes of a No-Limit Hold’em Engine*, documents the project’s mathematical and algorithmic design. It covers poker rules and hand frequencies, probability and game theory, card representation and shuffling, evaluator architectures, equity estimation, betting-state transitions, pot settlement, decision-policy concepts, opponent profiling, system invariants, complexity discussion, and a worked hand.

**How to use it:** use the report as the mathematical reference, and consult the notebook for corresponding executable examples.

## Suggested repository layout

```text
.
├── index.html
├── README.md
├── no_limit_holdem_engine_algorithms.ipynb
└── algorithms_of_a_no_limit_holdem_engine.pdf
```

Rename the provided files to these names when adding them to the repository, or update the paths in this README to match your filenames.

## Suggested way to explore

1. Open the hosted webpage and play a few hands to understand the interface and hand progression.
2. Read the report sections on hand evaluation, equity, betting logic, and pot settlement.
3. Run the corresponding notebook cells to inspect the calculations, examples, and invariant checks.

## Scope and limitations

This is an educational and experimental project. The notebook and report describe the approaches and checks included in the implementation; they do not establish that every component is production-hardened, that the AI plays optimally, or that the browser game is a server-authoritative online poker platform.
