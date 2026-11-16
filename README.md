# Football qui va gagner

Notebooks and submission files for a football match-outcome challenge. Each match is labeled as one of three results: a home win, a draw, or an away win.

## What is in this repository

| File | Role |
| --- | --- |
| `Y_train_1rknArQ.csv` | Training labels. Columns are `ID`, `HOME_WINS`, `DRAW`, and `AWAY_WINS`, with exactly one outcome set to `1`. |
| `Y_train_supp.csv` | Extra training target, `GOAL_DIFF_HOME_AWAY`. |
| `Y_test_random_sEE2QeA.csv` | Test labels in the same one-hot format as the training file. |
| `benchmark_notebook.ipynb` | XGBoost benchmark. It models away wins and writes `benchmark_submission.csv`. |
| `Logistic_notebook.ipynb` | Same starting point, then a logistic regression on selected features. |
| `Lasso_notebook .ipynb` | LassoCV experiment on the goal-difference target. The filename contains a space. |
| `benchmark_submission.csv`, `Badre_submission.csv`, `Badre_submission_HOME_WIN.csv` | Predictions with columns `ID`, `HOME_WINS`, `DRAW`, `AWAY_WINS`. |

The home and away team-statistics tables that the notebooks load are not in this repository. Each notebook still points `read_csv` at absolute paths on the original machine.

## How to run

From the repository root:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install pandas numpy scikit-learn xgboost matplotlib seaborn tqdm jupyter
jupyter notebook
```

Open `benchmark_notebook.ipynb` first. Before you run the cells, point the `read_csv` calls at your local copies of `train_home_team_statistics_df.csv`, `train_away_team_statistics_df.csv`, and the matching test files. The notebook treats a constant home-win prediction as the simple baseline. A submission row must keep exactly one of `HOME_WINS`, `DRAW`, or `AWAY_WINS` equal to `1`.
