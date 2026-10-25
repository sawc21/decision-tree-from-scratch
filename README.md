# Decision Trees: Entropy, Information Gain, and Game Outcomes

An explainable walkthrough of decision-tree construction using a 20-record classroom dataset. The notebooks calculate entropy and information gain directly, show why each split is selected, and compare the resulting logic with an entropy-based scikit-learn decision tree.

## What this project explores

- Parent entropy, branch weights, weighted entropy, and information gain.
- Selecting splits from graphics, multiplayer, and marketing features.
- Following individual records through the tree and inspecting majority-class leaves.
- Encoding categorical features and visualizing a fitted decision tree.

[decision_tree.ipynb](decision_tree.ipynb) contains the complete walkthrough, tree visualization, and record tracing. [entropy_exploration.ipynb](entropy_exploration.ipynb) is an earlier, shorter exploration of the graphics split. The included dataset is [data/game_success.csv](data/game_success.csv).

## Results and limitations

The first split is **Has High Graphics?**, with information gain of approximately **0.6166**. The fitted tree classifies **19 of 20 training records correctly (95%)**. Record 19 shares the same feature values as records with the opposite label, so the final leaf uses the majority class.

This is a teaching example with evaluation on the training data. It does not measure generalization or predict commercial game success. Split calculations are implemented manually; the final classifier and plot use scikit-learn. The walkthrough selects branches explicitly rather than providing a general recursive tree-building library.

## Run it

Use Python 3.14.7, the version used for validation. From the repository root, create a virtual environment and install the direct dependencies.

Windows (PowerShell):

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

macOS/Linux:

```sh
python3 -m venv .venv
./.venv/bin/python -m pip install -r requirements.txt
```

Open either notebook in a Jupyter-compatible editor using that environment. Start from the repository root so the relative CSV path resolves, restart the kernel, and run all cells in order.

In VS Code, open the notebook, choose **Select Kernel > Python Environments**, and select this repository's `.venv` interpreter. Other Jupyter-compatible editors should use the same interpreter.
