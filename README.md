# ML Domain Recruitment Task Submission

This repository contains a Jupyter Notebook submission for the ML Domain recruitment task using the UCI Cleveland Heart Disease dataset. The analysis predicts serum cholesterol (`chol`) with a linear regression model after inspecting, cleaning, and engineering features from the dataset.

## Files

- `Candidate_Name_MLTask.ipynb` — the main notebook containing all code, visible outputs, visualisation cells, and written interpretations for the four required phases.

> Before final portal submission, rename the notebook from `Candidate_Name_MLTask.ipynb` to the required `FirstName_LastName_MLTask.ipynb` format using the submitter's real name.

## Task Coverage

The notebook is organized around the four requested phases:

1. **Understanding the Data**
   - Confirms the raw dataframe shape is 303 rows by 14 columns.
   - Prints dtypes and identifies `ca` and `thal` as object columns caused by `?` missing markers.
   - Counts missing `?` values per column.
   - Prints numerical summaries and discusses plausible/extreme clinical values.
   - Includes exploratory visualisation code and written interpretations.

2. **Data Cleaning**
   - Converts `?` values to nulls.
   - Imputes `ca` with the median and `thal` with the mode.
   - Casts columns to appropriate numeric/categorical-compatible dtypes.
   - Checks and removes exact duplicates if present.
   - Documents why extreme but clinically possible values are retained.
   - Uses one-hot encoding with a dropped reference category for the linear model.

3. **Feature Engineering**
   - Adds `age_thalach_load` to combine age and achieved maximum heart rate.
   - Adds `bp_st_depression_flag` for elevated resting blood pressure plus ST depression.
   - Adds `age_risk_group` based on clinically interpretable age thresholds.
   - Visualises engineered feature relationships with cholesterol and explains the rationale.

4. **Linear Regression and Interpretation**
   - Uses an 80/20 train-test split.
   - Fits a `LinearRegression` model through a preprocessing pipeline.
   - Reports test R² and MAE.
   - Prints coefficients and identifies the three largest absolute coefficients.
   - Interprets those coefficients in practical terms and discusses model limitations.

## Environment

The notebook expects a Python 3 environment with the following packages installed:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

The dataset is loaded from a public raw CSV URL in the notebook. If your execution environment blocks internet access, download the Cleveland heart disease CSV manually and update the `url` variable in the first notebook code cell to point to the local file path.



## Notes for Reviewers

- The model's low or negative R² is not treated as a failure; the notebook explicitly explains that cholesterol is difficult to predict from this small feature set.
- Coefficients are interpreted as descriptive linear associations, not causal clinical findings.
- Cleaning decisions are documented in prose instead of being hidden inside an unexplained pipeline.
