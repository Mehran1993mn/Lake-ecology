# {{ National-Scale Machine Learning Assessment of Lake Ecological Status under the EU WFD }}

**Author:** {{ Mehran Mahdian }}  
**Contact:** {{ Mehran.mahdian@uef.fi }}
**Organization:** {{ University of Eastern Finland }}
**Website:** {{ https://www.linkedin.com/in/mehran-mahdian1993/
https://scholar.google.com/citations?user=GWxu7rQAAAAJ&hl=en&oi=ao}}

 ## Project Overview
{{ cookiecutter.description }}
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


