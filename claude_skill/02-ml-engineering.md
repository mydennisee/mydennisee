# 02 — ML Engineering & Model Development

## What I Do

Build end-to-end machine learning systems across the full CRISP-DM lifecycle — from business problem framing through feature engineering, model development, evaluation, and production deployment. Specialise in classification, scoring, and segmentation problems in regulated environments.

---

## How I Approach It

### Problem Framing (Before Any Code)
- What decision does this model support?
- What is the cost of a false positive vs. false negative in this context?
- What is the baseline — rules-based system, human judgment, random?
- What does "good enough" look like for this stakeholder?

### Feature Engineering
- Domain knowledge first — what signals logically predict the target?
- SCD-2 design for time-aware features in historical datasets
- Feature store patterns for reuse across models in the same domain
- Avoid data leakage: enforce strict temporal cutoffs per training window

### Model Development
- Start with interpretable baselines (logistic regression, decision tree) before complex models
- XGBoost as the primary workhorse for tabular, structured data
- SMOTE / class weight adjustment for imbalanced targets (credit risk, churn)
- Hyperparameter tuning: Bayesian search over grid search where feasible

### Evaluation
- Segment-level performance — aggregate metrics hide underperforming cohorts
- Precision/recall trade-off explicitly documented and signed off by business
- SHAP values for global and local explainability — mandatory, not optional
- Shadow scoring before production cutover

### Threshold Optimisation
- Treat decision threshold as a business decision, not a technical default
- K-Means or quantile segmentation to define optimal bands
- Present threshold sensitivity as a table — show business the range of outcomes

---

## CRISP-DM Flow

```
Business Understanding → Data Understanding → Data Preparation
→ Modelling → Evaluation → Deployment → [Iterate]
```

Each phase has an explicit deliverable and sign-off point.

---

## Tools & Stack

| Category | Tools |
|----------|-------|
| Core ML | XGBoost, Scikit-learn, PyTorch |
| Explainability | SHAP, feature importance, partial dependence plots |
| Imbalance | SMOTE, class weighting, stratified sampling |
| Validation | A/B test design, shadow scoring, pilot validation |
| Tracking | MLflow (experiment tracking), versioned artefacts |

---

## Demonstrated Work

- **Collections Scoring System** — Three-phase XGBoost pipeline (prevention / intervention / recovery). SMOTE for class imbalance. Targeted 5–10% delinquency flow reduction. Full A/B test design and pilot validation.
- **AML/CFT Analytics Framework** — K-Means segmentation + threshold optimisation. ~25% reduction in false positives. SHAP explainability presented to C-suite and BNM.
- **Churn Prediction & Retention** — Predictive churn model with SHAP-driven retention targeting. 55–85% reduction in churn rate at intervention cohorts.

---

## My Standard: What "Done" Looks Like

- Baseline comparison documented and shared with business
- Segment-level metrics reviewed — not just aggregate
- SHAP plots produced and interpretable by a non-technical stakeholder
- Threshold decision signed off by the relevant business owner
- Shadow scoring period completed before live deployment
