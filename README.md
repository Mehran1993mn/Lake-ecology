# {{ National-Scale Machine Learning Assessment of Lake Ecological Status under the EU WFD }}

**Author:** {{ Mehran Mahdian }}  
**Contact:** {{ Mehran.mahdian@uef.fi }}
**Organization:** {{ University of Eastern Finland }}
**Website:** {{ https://www.linkedin.com/in/mehran-mahdian1993/
https://scholar.google.com/citations?user=GWxu7rQAAAAJ&hl=en&oi=ao}}

 ## Project Overview

## Problem Statement

Lakes provide critical ecosystem services including biodiversity support, drinking water, fisheries, and recreation. However, anthropogenic pressures and climate change are accelerating eutrophication, browning, and oxygen depletion.
Under the EU Water Framework Directive (WFD), ecological status is assessed using biological quality elements. These assessments are:
*Expensive
*Labor intensive
*Temporally sparse
*Not near–real-time
There is currently no national-scale framework that predicts WFD ecological status using only routinely measured physicochemical variables.

## Challenge Statement

WFD ecological classification is difficult to model because:
*Ecological classes overlap 
*Class imbalance exists 
*Relationships are nonlinear and multivariate

##Solution Statement
This study develops a national-scale machine learning framework that:
*Uses only routine water-quality and morphometric variables
*Compares RF, XGBoost, SVM, ANN, and TabNet
*Implements a Bayesian Neural Network (BNN)
*Decomposes uncertainty into aleatoric and epistemic components
*Applies SHAP and permutation importance for interpretability

##Objectives

*Classify WFD ecological status from routine variables.
*Identify dominant environmental drivers.
*Quantify predictive uncertainty.
*Provide a scalable complement to biological WFD monitoring.

##Literature Review (Foundational Methods)

This workflow builds upon:
*Breiman (2001) – Random Forest
*Cortes & Vapnik (1995) – Support Vector Machine
*Chen & Guestrin (2016) – XGBoost
*Arik & Pfister (2021) – TabNet
*Lundberg & Lee (2017) – SHAP
*Bayesian Neural Networks with variational inference

##Research Questions

RQ1:
Can routine water-quality variables predict WFD ecological status at national scale?
RQ2:
Which environmental variables most influence classification?
RQ3:
Does Bayesian modeling improve probability calibration?
RQ4:
Is predictive uncertainty primarily aleatoric or epistemic?

## Data Sources

Study Area
Finland
2,487 lakes
Monitoring period: 2012–2017
Surface samples (0–2 m depth)
Lake-wise aggregated means
Training and testing data are drawn from the same monitoring period using 5-fold cross-validation.

### Published Data Sources

| Name | Source | Description | Access Method | data DOI/url | metadata DOI/URL| details | data citation |
|----Hertta--|----SYKE----|-----Water quality and WFD ecological status--------|------Open access---------|---------https://www.syke.fi/en/environmental-data/open-web-services/environmental-data-apis#directory-----|-----------------|---------|---------------|

### Data Access Notes

Data are publicly availabe

### Inputs folder
https://www.syke.fi/en/environmental-data/open-web-services/environmental-data-apis#directory

## Methods Summary

Model Framework

Machine Learning and Deep Learning classification framework.

Preprocessing Steps

Surface filtering (0–2 m)

Lake-wise aggregation (2012–2017 mean)

kNN imputation (<6% missing data)

MWMOTE oversampling (training folds only)

5-fold cross-validation

Optuna

Models

Random Forest

XGBoost

SVM

ANN (MLP)

TabNet

Bayesian Neural Network (variational inference)

Interpretability

Permutation importance

SHAP analysis

Kruskal–Wallis statistical testing

Evaluation Metrics

F1-score (primary)

Accuracy

MCC

Brier score

Expected Calibration Error (ECE)

Repository Structure
Folder/File	Description
notebooks/	Analysis notebooks
inputs/	Minimal metadata and configuration files
processed_data/	Analysis-ready datasets
model_data/	Trained models and predictions
figures/	Figures used in manuscript
run_reproducibility.py	Reproducibility wrapper
Dockerfile	Reproducible container
CITATION.cff	Citation metadata

How to Reproduce
Computational Requirements

Python 3.10+

16 GB RAM recommended

Optional GPU for BNN

OS: Windows / Linux / macOS


Run the Code
pip install -r requirements.txt
python run_reproducibility.py

Results

Key findings:

Best multi-class macro-F1 ≈ 0.65

Binary F1 ≈ 0.84

BNN achieved best calibration (ECE = 0.016)

TP, TN, and turbidity are dominant predictors

Moderate class most difficult

Uncertainty primarily aleatoric

Citation

DOI: DOI_PENDING

License

MIT License










