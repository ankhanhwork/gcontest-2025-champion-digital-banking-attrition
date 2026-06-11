# Methodology

## 1. Business Framing

The unit of observation in the source data was an onboarding attempt, while
the main prediction target concerned the customer's final outcome. We
therefore separated event-level funnel analysis from customer-level modeling
to avoid treating repeated attempts as independent customers.

The primary modeling question was:

> Given a customer's profile, context, and history before the final recorded
> attempt, how well can we rank the risk that the customer will drop off?

## 2. Data Preparation

The preparation workflow covered:

- standardized column names and categorical values;
- timestamp parsing and chronological ordering by customer;
- consistency-based filling for stable customer attributes;
- context-aware treatment of selected device fields;
- explicit checks for missingness and implausible ages;
- derived attempt duration and journey sequence;
- removal of temporary analysis columns before modeling.

Data imputation was applied conservatively. Values shared across a customer's
own attempts were preferred over population-level assumptions.

## 3. Exploratory Analysis

Exploration was organized around three views:

- **Funnel performance:** completion, failure, pending status, and stop-point
  concentration.
- **Customer cohorts:** age generation, gender, phone manufacturer, operating
  system, and retry behavior.
- **Journey context:** hour, weekday, office hours, duration, sequence, and
  repeated failure history.

This stage identified OCR and OTP as the dominant operational bottlenecks and
showed that failure recovery behavior mattered in addition to demographics.

## 4. Feature Engineering

Customer-level predictors included:

- encoded gender, generation, and phone manufacturer;
- hour of day, day of week, weekend, and office-hour flags;
- cumulative attempt count before the current event;
- cumulative failed and pending attempts;
- historical counts for each stop point;
- manually ordered stop-point representation;
- device and OS context where available.

Historical features were calculated chronologically so that the current
record did not contribute to its own predictors.

## 5. Model Development

Three tree-based classifiers were compared:

- XGBoost;
- LightGBM;
- Random Forest.

The workflow used stratified cross-validation and imbalance-aware evaluation.
ROC-AUC was the primary model-ranking metric because the business use case was
to prioritize risk, while precision, recall, F1, and accuracy were retained
for operational interpretation.

Reported cross-validation results:

| Model | ROC-AUC | Accuracy | F1 | Precision | Recall |
|---|---:|---:|---:|---:|---:|
| XGBoost | 0.8943 | 0.9287 | 0.5462 | 0.4742 | 0.6463 |
| LightGBM | 0.8927 | 0.9303 | 0.5442 | 0.4808 | 0.6281 |
| Random Forest | 0.8907 | 0.9351 | 0.5255 | 0.5100 | 0.5438 |

XGBoost was selected for its leading ROC-AUC and recall.

## 6. Explainability

SHAP was used to inspect global feature importance and the direction of
individual feature effects. The interpretation focused on risk signals that
could be mapped to product interventions rather than treating model
importance as proof of causality.

## 7. Survival Analysis

Kaplan-Meier curves were used to compare continuation behavior across
customer, device, and time cohorts. Log-rank tests supported group
comparisons, while a Cox proportional hazards model provided a multivariate
view of factors associated with abandonment timing.

Survival analysis complemented classification by describing not only whether
a customer left, but how persistence changed over repeated attempts.

## 8. Step-Specific Models

Separate classifiers were explored for OTP, OCR, privacy, selfie, contract,
and other failure steps. Their ROC-AUC values were generally around 0.5-0.6.
These models were not considered reliable enough for deployment.

This negative result is important: step-level feature importance was used only
as directional evidence, and recommendations relied more heavily on funnel
concentration, cohort analysis, domain research, and the stronger overall
drop-off model.

## 9. Limitations

- The source covered only the first quarter of 2024.
- Observational associations do not establish causal effects.
- Some timestamps and device attributes required quality treatment.
- Financial impact was estimated from an external acquisition-cost
  assumption.
- A production model would require temporal validation, probability
  calibration, monitoring, fairness review, and prospective testing.
