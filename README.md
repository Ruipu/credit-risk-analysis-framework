# Credit Risk Analysis Framework

This repository presents a structured credit risk analysis framework built using the German Credit dataset.

The project focuses on interpretable risk modeling, scenario-based analysis, and portfolio-level risk evaluation, rather than machine learning prediction.

Instead of training a black-box model, this project constructs a rule-based credit risk scoring system that translates borrower characteristics into a risk score, a pseudo probability of default (pseudo PD), and risk categories.

The framework is then extended to analyze how borrower and portfolio risk evolve under different conditions, including baseline, sensitivity, stress scenarios, and risk migration.

---

## Project Structure

credit-risk-validation/  
├── data/  
├── model.ipynb  
├── sensitivity_analysis.ipynb  
├── stress_testing.ipynb  
├── migration_matrix.ipynb  
└── README.md  

---

## Project Overview

This repository contains four connected components.

### 1. Baseline Credit Risk Scoring

This module builds an interpretable, rule-based credit risk scoring framework.

Borrower characteristics such as age, job, housing, savings, checking accounts, credit amount, and loan duration are mapped into structured numeric scores.

These inputs are combined into a risk score using intuitive credit risk logic, and then transformed into a pseudo probability of default.

Borrowers are further grouped into four categories: Low, Moderate, Elevated, and High risk.

This step establishes the baseline risk distribution of the portfolio.

---

### 2. Sensitivity Analysis

This module evaluates how the risk framework responds to small changes in borrower conditions.

Mild shocks are applied to borrower features, including increases in loan size and duration, as well as deterioration in savings.

The resulting pseudo PD is compared with the baseline to assess whether the model reacts in a directionally consistent and economically intuitive way.

---

### 3. Stress Testing

This module analyzes how the entire portfolio behaves under adverse conditions.

Two scenarios are constructed:

**Mild stress:**
- Credit amount increases by 20 percent  
- Duration increases by 30 percent  
- Savings and checking conditions deteriorate  

**Severe stress:**
- Credit amount increases by 30 percent  
- Duration increases by 50 percent  
- Savings and checking conditions drop to the lowest level  

For each scenario, borrower-level risk and portfolio-level metrics are recomputed, including average risk, median risk, and the share of high-risk borrowers.

---

### 4. Risk Migration Analysis

This module examines how borrowers move across risk categories under stress.

Migration matrices are constructed to compare baseline risk categories with those under stress scenarios.

This allows the analysis to capture how risk shifts across the portfolio, including movement from low to moderate risk and from elevated to high risk.

---

## Methodology

The framework emphasizes interpretability and structured reasoning.

A rule-based scoring system is used to assign risk contributions based on borrower characteristics.

- Larger credit amount → higher risk  
- Longer duration → higher risk  
- Stronger savings and checking → lower risk  
- More stable housing and job conditions → lower risk  

The resulting score is transformed into a pseudo probability of default using a logistic function.

This value is used for comparison across scenarios rather than as a calibrated default probability.

---

## Key Questions

This project addresses several key questions:

- What does the baseline risk distribution look like?  
- Does the model respond appropriately to small borrower-level changes?  
- How does portfolio risk evolve under adverse scenarios?  
- Which borrowers are most vulnerable under stress?  
- How does risk shift across categories when conditions deteriorate?  

---

## Main Insights

The results show that borrower risk increases consistently under both mild and severe stress scenarios.

Risk does not only increase on average. It also concentrates in higher-risk segments as borrower conditions worsen.

Under severe stress, a substantial portion of borrowers moves into elevated and high-risk categories, indicating increased portfolio vulnerability.

---

## Tools Used

- Python  
- pandas  
- NumPy  
- matplotlib  
- Jupyter Notebook  

---

## Notes

This project is designed as an analytical framework rather than a production risk model.

- Model weights are manually specified  
- Pseudo PD is illustrative  
- The focus is on interpretability and scenario analysis  

The goal is to demonstrate how borrower characteristics can be translated into a structured and explainable risk analysis workflow.

---

## Author

**Ruipu Gao**  
PhD Candidate in Economics  
