# Explainable Machine Learning for Continuous Household Welfare Prediction

This repository contains the research notebook supporting the study **“Explainable Machine Learning for Continuous Household Welfare Prediction Using the Tanzania National Panel Survey: Toward Trustworthy AI for Official Statistics.”**

The analysis predicts the natural logarithm of real total consumption expenditure per adult equivalent over 28 days using non-consumption household characteristics from Tanzania’s National Panel Survey (NPS) 2020/21, Wave 5.

## Analytical workflow

The notebook covers:

- validation of the constructed household-level analytical dataset;
- redundancy screening and target-leakage auditing;
- training and comparison of Dummy, Linear, Ridge, Random Forest, and XGBoost regressors;
- five-fold cross-validation and held-out evaluation using RMSE, MAE, and R²;
- global and local SHAP explanations;
- sensitivity analysis excluding welfare-proximal predictors;
- subgroup error diagnostics; and
- survey-weighted performance evaluation.

## Repository files

- `Manuscript_Aligned_Household_Welfare_Analysis.ipynb` — manuscript-aligned analytical workflow.
- `requirements.txt` — Python dependencies required to run the notebook.
- `.gitignore` — prevents raw survey data and generated household-level files from being committed.

## Data access

Raw NPS microdata and the derived household-level analytical dataset are not distributed with this repository. Users must obtain authorised access to the Tanzania NPS 2020/21 Wave 5 files and comply with the applicable data-use conditions. The notebook expects an authorised `analysis_data.pkl` file in its working directory.

Do **not** upload raw `.dta` files, intermediate `.pkl` files, or household-level derived datasets to a public GitHub repository.

## Reproduction

1. Create and activate a Python 3.12 environment.
2. Install the required packages:

   ```bash
   pip install -r requirements.txt
   ```

3. Place the authorised `analysis_data.pkl` file in the notebook working directory.
4. Open `Manuscript_Aligned_Household_Welfare_Analysis.ipynb`, restart the kernel, and select **Run All**.

The workflow uses a fixed random seed of 42 for train–test splitting, cross-validation, and model development.

## Main study configuration

| Item | Value |
|---|---:|
| Households | 4,709 |
| Initial candidate predictors | 123 |
| Core predictors | 109 |
| Restricted sensitivity predictors | 102 |
| Training/test split | 80% / 20% |
| Cross-validation | Five-fold |

## Authors

- Rabia Omar Said — corresponding author
- Abdi Talib Abdalla
- Abubakar Diwani Bakari

Department of Computer Science and Information Technology, School of Computing, Communication and Media Studies, The State University of Zanzibar, Zanzibar, Tanzania.

## Citation

Citation details will be added after publication.

## Licence and data responsibility

The source code may be reused subject to the repository licence. The NPS microdata remain governed by the conditions imposed by their data provider and are not covered by the code licence.
