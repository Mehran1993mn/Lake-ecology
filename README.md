# 🇫🇮 National-Scale Machine Learning Assessment of Lake Ecological Status under the EU WFD

---

**Author:** Mehran Mahdian  
**Contact:** Mehran.mahdian@uef.fi  
**Organization:** University of Eastern Finland  
**Website:**  
- [LinkedIn](https://www.linkedin.com/in/mehran-mahdian1993/)  
- [Google Scholar](https://scholar.google.com/citations?user=GWxu7rQAAAAJ&hl=en&oi=ao)

---

# 🌍 Project Overview

## 📌 Problem Statement

Lakes provide critical ecosystem services including biodiversity support, drinking water, fisheries, and recreation. However, anthropogenic pressures and climate change are accelerating:

- Eutrophication  
- Browning  
- Oxygen depletion  

Under the **EU Water Framework Directive (WFD)**, ecological status is assessed using biological quality elements. These assessments are:

- Expensive  
- Labor intensive  
- Temporally sparse  
- Not near–real-time  

There is currently **no national-scale framework** that predicts WFD ecological status using only routinely measured physicochemical variables.

---

## ⚠️ Challenge Statement

WFD ecological classification is difficult to model because:

- Ecological classes overlap (especially the *Moderate* class)  
- Class imbalance exists (few Bad/Poor lakes)  
- Relationships are nonlinear and multivariate  
- Ecological boundaries are transitional and noisy  

---

## 💡 Solution Statement

This study develops a **national-scale machine learning framework** that:

- Uses only routine water-quality and morphometric variables  
- Compares **RF, XGBoost, SVM, ANN, and TabNet**  
- Implements a **Bayesian Neural Network (BNN)**  
- Decomposes uncertainty into **aleatoric and epistemic components**  
- Applies **SHAP and permutation importance** for interpretability  
- Evaluates probabilistic calibration (ECE & Brier score)

---

## 🎯 Objectives

- Classify WFD ecological status from routine variables  
- Identify dominant environmental drivers  
- Quantify predictive uncertainty  
- Provide a scalable complement to biological WFD monitoring  

---

## 📚 Literature Review (Foundational Methods)

This workflow builds upon foundational machine learning and explainability methods:

- Breiman (2001) – Random Forest  
- Cortes & Vapnik (1995) – Support Vector Machine  
- Chen & Guestrin (2016) – XGBoost  
- Arik & Pfister (2021) – TabNet  
- Lundberg & Lee (2017) – SHAP  
- Bayesian Neural Networks with Variational Inference  

---

## 🔎 Research Questions

**RQ1:**  
Can routine water-quality variables predict WFD ecological status at national scale?

**RQ2:**  
Which environmental variables most strongly influence classification?

**RQ3:**  
Does Bayesian modeling improve probability calibration?

**RQ4:**  
Is predictive uncertainty primarily aleatoric or epistemic?

---

# 📊 Data Sources

## Study Area

- Country: **Finland**  
- Lakes: **2,487**  
- Monitoring Period: **2012–2017**  
- Surface samples: **0–2 m depth**  
- Aggregation: Lake-wise period means  

Training and testing use **5-fold cross-validation** within the same monitoring period.

---

## Published Data Sources

| Name    | Source | Description | Access | URL |
|---------|--------|------------|--------|-----|
| Hertta Database | SYKE | Water quality & WFD ecological status | Open access | https://www.syke.fi/en/environmental-data/open-web-services/environmental-data-apis#directory |

---

## Data Access Notes

Data are publicly available through SYKE open web services.

Users must download raw datasets and place them in the `inputs/` directory before running the workflow.

---

# ⚙️ Methods Summary

## 🧠 Model Framework

Supervised Machine Learning and Deep Learning classification framework.

---

## 🔄 Preprocessing Steps

- Surface filtering (0–2 m)
- Lake-wise aggregation (2012–2017 mean)
- kNN imputation (<6% missing data)
- MWMOTE oversampling (training folds only)
- 5-fold cross-validation
- Hyperparameter optimization using **Optuna**

---

## 🤖 Models

- Random Forest  
- XGBoost  
- SVM  
- ANN (MLP)  
- TabNet  
- Bayesian Neural Network (Variational Inference)

---

## 🔍 Interpretability

- Permutation importance  
- SHAP analysis  
- Kruskal–Wallis statistical testing  

---

## 📈 Evaluation Metrics

- F1-score (primary metric)  
- Accuracy  
- MCC  
- Brier score  
- Expected Calibration Error (ECE)

---

# 📁 Repository Structure

| Folder/File | Description |
|-------------|-------------|
| `notebooks/` | Analysis notebooks |
| `inputs/` | Minimal metadata and configuration files |
| `processed_data/` | Analysis-ready datasets |
| `model_data/` | Trained models and predictions |
| `figures/` | Figures used in manuscript |
| `run_reproducibility.py` | Reproducibility wrapper |
| `Dockerfile` | Reproducible container |
| `CITATION.cff` | Citation metadata |

---

# 🔁 How to Reproduce

## 💻 Computational Requirements

- Python 3.10+  
- 16 GB RAM recommended  
- Optional GPU for BNN  
- OS: Windows / Linux / macOS  

---

## ▶️ Run the Code

```bash
pip install -r requirements.txt
python run_reproducibility.py
