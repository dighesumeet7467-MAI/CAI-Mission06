# Mission 6 Solution — Autonomous Warp State Machine

This package contains the integrated Mission 6 deliverable, `ps06_solution.ipynb`. The notebook implements AURA's bounded state machine, validated tool dispatcher, MDP trajectory evaluator, and cycle-detection tripwire, followed by the four required assert-based test suites.

## Requirements

- Python 3.11 or later
- VS Code with the Python and Jupyter extensions, or Jupyter with `nbconvert` and `ipykernel`
- The notebook code itself uses only the Python standard library

## Run in VS Code

1. Open this folder in VS Code.
2. Open `ps06_solution.ipynb` and select a Python 3.11+ kernel.
3. Choose **Run All**.
4. Confirm the final cell prints `All four Mission 6 test suites passed.`

## Run from PowerShell

From this folder, install the notebook runner if needed:

```powershell
python -m pip install --user nbconvert ipykernel
```

Execute the notebook and save cell outputs back into it:

```powershell
python -m nbconvert --to notebook --execute --inplace .\ps06_solution.ipynb
```

## Notebook contents

- **State machine:** the seven required states, legal transition graph, and maximum 20-step budget.
- **Tool protocol:** the three specified tools, strict JSON-Schema contract checks for the supported schema keywords, and errors returned to the agent as observations.
- **MDP evaluator:** state-action-reward trajectory logging, discounted return with `gamma=0.95`, and a transition-frequency function for supplied historical records.
- **Cycle sentinel:** Floyd tortoise-and-hare cycle detection, stable state-action hashes, and an emergency halt with a critical security log.
- **Tests:** state machine and budget, invalid protocol payload, required discounted-return example, and cycle detection with halt before step 10.

## Historical data

The Mission 6 materials available with this project did not include a historical jump dataset or instructions for downloading one. The notebook does not fabricate historical records. `transition_frequency_matrix(...)` returns an empty result when no dataset is supplied; use it with real course-provided records if they become available.

## Submission

The Mission 6 PDF specifies `ps06_solution.ipynb` as the deliverable. Submit that notebook through the course's Canvas command terminal. This README is a guide for running the notebook.
