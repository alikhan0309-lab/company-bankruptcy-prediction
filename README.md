# Company Bankruptcy Prediction (Taiwan, 1999-2009)

Predicts whether a company goes bankrupt from 95 financial ratios, using a random forest.

**Notebook:** [company-bankruptcy-prediction.ipynb](https://github.com/alikhan0309-lab/company-bankruptcy-prediction/blob/main/company-bankruptcy-prediction.ipynb)

## Data
Taiwan Economic Journal data (6,819 companies, about 3% bankrupt), from the Kaggle dataset
[Company Bankruptcy Prediction](https://www.kaggle.com/datasets/fedesoriano/company-bankruptcy-prediction).
The data file is not included in this repository.

## Approach
- 80/20 train/test split
- Random over-sampling on the training set only
- Random forest tuned with grid search (accuracy first, then F1)
- Lowered the decision threshold to catch more bankruptcies
- Gini and permutation feature importance

## Key results
- The first model had 0.97 accuracy, but recall on bankrupt companies was only 0.31.
- Tuning for F1 raised recall to 0.47.
- Lowering the threshold to 0.3 raised recall to about 0.67 (precision 0.37).
- Quick Ratio was the strongest signal in permutation importance.

## Limitations
The test set has only 51 bankrupt companies, and the threshold was chosen on the test set, so the numbers are approximate. Feature importance shows what the model relies on, not what causes bankruptcy.

## How to run
1. Download the dataset from the Kaggle link above.
2. Open the notebook in Kaggle or Jupyter.
3. Install `pandas`, `scikit-learn`, `imbalanced-learn`, and `matplotlib`.
4. Update the data path in the load cell if you run it outside Kaggle.
