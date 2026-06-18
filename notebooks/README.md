# Public Analysis Notebooks

These notebooks are split from the original G'Contest final-round working
notebook so GitHub can render the analysis faster and reviewers can inspect
the public portfolio flow independently.

Raw data and data-loading code are intentionally excluded from this public
version. Saved notebook outputs are preserved, so charts, SHAP visuals, and
model metrics remain visible for interview review. The notebooks are meant
for analytical walkthroughs rather than end-to-end reruns.

## Reading Order

1. [Business, Data Preparation, and EDA](01-business-data-eda.ipynb)
2. [Preprocessing and Final-Attempt Drop-Off Modeling](02-preprocessing-dropoff-modeling.ipynb)

## Review Notes

- The public scope covers business framing, data preparation, exploratory
  analysis, preprocessing, final-attempt drop-off prediction, and XGBoost SHAP
  interpretation.
- Step-specific failure modeling and other exploratory analytical methods are
  intentionally excluded from this portfolio version.
- Dependency installation commands are left in context where they explain
  required libraries such as SHAP and CatBoost.
