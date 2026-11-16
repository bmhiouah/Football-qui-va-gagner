# Contributing

Small, reviewable changes are the easiest to merge. This note covers the two things that are easy to get wrong in this repository.

## Notebooks

- Edit `benchmark_notebook.ipynb`, `Logistic_notebook.ipynb`, or `Lasso_notebook .ipynb` instead of adding a near-copy. The Lasso filename includes a trailing space; keep that name so existing links still resolve.
- When you change a `read_csv` path, use a path relative to the repository. Do not commit an absolute path from your own machine.
- If you quote an accuracy, name the split. The benchmark uses `train_test_split` with `train_size=0.8` and `random_state=42`, twice (train/test, then train/validation).

## Submission files

Prediction files use the columns `ID`, `HOME_WINS`, `DRAW`, and `AWAY_WINS`. Each row is one-hot: exactly one of the three outcome columns is `1`.

Leave `Y_train_1rknArQ.csv`, `Y_train_supp.csv`, and `Y_test_random_sEE2QeA.csv` unchanged. Those files are the challenge labels, not model output.
