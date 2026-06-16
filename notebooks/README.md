# Full Analysis Notebooks

These notebooks are split from the original G'Contest final-round working notebook so GitHub can render the analysis faster and reviewers can inspect each stage independently.

Raw data and data-loading code are intentionally excluded from this public portfolio version. Saved notebook outputs are preserved, so charts, tables, and model metrics remain visible for review. The notebooks are meant for interview discussion and analytical walkthroughs rather than end-to-end reruns.

## Reading Order

1. [Business Understanding](01-business-understanding.ipynb)
2. [Data Preparation](02-data-preparation.ipynb)
3. [Exploratory Data Analysis](03-eda.ipynb)
4. [Data Preprocessing](04-data-preprocessing.ipynb)
5. [Drop-Off Prediction Modeling](05-dropoff-modeling.ipynb)
6. [Step Failure Modeling](06-step-failure-modeling.ipynb)
7. [Survival Analysis](07-survival-analysis.ipynb)

## Review Notes

- The code logic is retained from the original working notebook as much as possible.
- Data input/export cells were removed to keep the repository data-free.
- Dependency installation commands are left in context where they explain required libraries such as SHAP and lifelines.
