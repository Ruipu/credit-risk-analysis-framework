# Credit Risk Scoring, Stress Testing, and Risk Migration Analysis

This repository presents a structured **credit risk analysis framework** built using the German Credit dataset.  
The project focuses on **interpretable risk modeling**, **scenario-based analysis**, and **portfolio-level risk monitoring** rather than pure machine learning prediction.

Instead of training a black-box model, this project develops a **rule-based credit risk scoring framework** that translates borrower characteristics into:

- a **risk score**
- a **pseudo probability of default (pseudo PD)**
- **risk buckets** for portfolio segmentation

The framework is then extended to evaluate how borrower and portfolio risk evolve under:

- baseline conditions
- mild borrower deterioration
- adverse stress scenarios
- risk migration across categories

---

## Project Structure

```text
credit-risk-validation/
├── data/
├── model.ipynb
├── sensitivity_analysis.ipynb
├── stress_testing.ipynb
├── migration_matrix.ipynb
└── README.md

Project Overview

This repository contains four connected components:

1. Baseline Credit Risk Scoring Framework

Builds an interpretable, rule-based credit risk scoring system using borrower-level characteristics such as:
	•	Age
	•	Job
	•	Housing
	•	Saving accounts
	•	Checking account
	•	Credit amount
	•	Duration
	•	Purpose

Categorical variables are mapped into ordered scores, continuous variables are standardized, and a weighted risk score is constructed using credit risk intuition.

The risk score is then transformed into a pseudo probability of default (pseudo PD) and used to classify borrowers into four risk groups:
	•	Low
	•	Moderate
	•	Elevated
	•	High

This notebook establishes the baseline portfolio risk distribution.

⸻

2. Sensitivity Analysis

Evaluates whether the scoring framework responds appropriately to small, controlled deteriorations in borrower characteristics.

The sensitivity scenario applies mild shocks such as:
	•	Credit amount +10%
	•	Duration +20%
	•	Saving accounts deteriorating by one category

The resulting pseudo PD is compared with the baseline case to assess whether the framework is:
	•	directionally consistent
	•	economically intuitive
	•	responsive to borrower-level deterioration

⸻

3. Stress Testing

Extends the framework to portfolio-level adverse scenario analysis.

Two stress scenarios are constructed:

Mild Stress
	•	Credit amount +20%
	•	Duration +30%
	•	Saving accounts deteriorate by one category
	•	Checking account deteriorates by one category

Severe Stress
	•	Credit amount +30%
	•	Duration +50%
	•	Saving accounts set to "little"
	•	Checking account set to "little"

For each scenario, the framework recomputes:
	•	borrower-level pseudo PD
	•	portfolio-level average risk
	•	median pseudo PD
	•	share of high-risk borrowers

This allows the project to measure how overall portfolio risk changes under worsening borrower conditions.

⸻

4. Risk Migration Analysis

Analyzes how borrowers move between risk buckets under stress.

Migration matrices are constructed for:
	•	Baseline → Mild Stress
	•	Baseline → Severe Stress

This step shows how risk is reallocated across the portfolio, highlighting:
	•	upward migration from Low to Moderate
	•	migration from Moderate to Elevated
	•	concentration of vulnerable borrowers in High-risk segments under severe stress

Risk migration adds a portfolio monitoring and validation perspective to the project.

⸻

Methodology

The framework is intentionally designed to emphasize interpretability.

Step 1: Rule-Based Risk Construction

Instead of fitting a statistical default model, the project manually assigns risk directions and weights based on basic credit risk logic.

Examples:
	•	larger credit amount → higher risk
	•	longer duration → higher risk
	•	stronger savings and checking positions → lower risk
	•	more stable housing and job conditions → lower risk

Step 2: Pseudo PD Transformation

The rule-based risk score is passed through a logistic transformation to create a bounded pseudo probability of default.

This pseudo PD should be interpreted as a risk-oriented probability-style measure, not as a production or regulatory PD estimate.

Step 3: Scenario Analysis

The same scoring logic is applied under baseline, sensitivity, and stress conditions to study how borrower and portfolio risk evolve.

Step 4: Portfolio Segmentation and Migration

Borrowers are grouped into risk buckets and tracked across scenarios to evaluate concentration and migration under adverse conditions.

⸻

Key Analytical Questions

This repository is designed to answer the following questions:
	1.	What does the baseline borrower risk distribution look like?
	2.	Does the risk framework respond sensibly to mild borrower deterioration?
	3.	How much does overall portfolio risk increase under adverse stress scenarios?
	4.	Which borrowers are most vulnerable under stress?
	5.	How does risk migrate across categories under worsening conditions?

⸻

Main Takeaways

This project demonstrates how a simplified but interpretable credit risk framework can be used to study:
	•	borrower-level vulnerability
	•	portfolio-level deterioration
	•	scenario-based risk escalation
	•	migration into higher-risk segments under stress

The results show that risk does not merely increase in average terms — it also concentrates and propagates across the portfolio under adverse conditions.

⸻

Why This Project Matters

This repository is especially relevant for roles in:
	•	Credit Risk
	•	Risk Analytics
	•	Model Validation
	•	Quantitative Risk
	•	Banking and Financial Analytics

The project emphasizes several skills commonly used in these settings:
	•	structured risk framework design
	•	scenario analysis
	•	sensitivity analysis
	•	stress testing
	•	portfolio segmentation
	•	migration analysis
	•	interpretable analytical modeling in Python

⸻

Tools Used
	•	Python
	•	pandas
	•	NumPy
	•	matplotlib
	•	Jupyter Notebook

⸻

Notes

This project is a demonstration framework, not a production risk system.

In particular:
	•	model weights are manually specified
	•	pseudo PD is illustrative rather than statistically calibrated
	•	the framework is intended to demonstrate risk logic, scenario analysis, and portfolio behavior

The goal is to show how borrower characteristics can be translated into a coherent and explainable risk analysis workflow.

⸻

Author

Ruipu Gao
PhD Candidate in Economics
Focus areas: applied analytics, causal inference, credit risk analytics, and interpretable quantitative modeling
