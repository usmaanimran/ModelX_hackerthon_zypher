<h1 align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Orbitron&weight=700&size=40&pause=1000&color=00FF99&center=true&vCenter=true&width=800&lines=Dementia+Prediction+AI;ModelX+Hackathon;By+Team+Zypher" alt="Typing SVG" />
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=Jupyter&logoColor=white" alt="Jupyter"/>
  <img src="https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn"/>
  <img src="https://img.shields.io/badge/XGBoost-17A8F5?style=for-the-badge&logo=xgboost&logoColor=white" alt="XGBoost"/>
</p>

<p align="center">
  <em>Predicting the likelihood of dementia using machine learning, built with a strict focus on ethical feature selection and data privacy.</em>
</p>

---


## 🚀 Project Overview

Dementia is a significant health challenge where early detection can lead to better management and care planning. This project utilizes the **Dementia Prediction Dataset** to build an optimized, highly accurate predictive model. 

We took a rigorous approach to **ethical AI**: over 900 "forbidden" medical variables were stripped from the dataset to prevent data leakage and ensure the model acts as a genuine screening aid rather than mimicking direct clinical tests.

---

## 🛠️ The Pipeline

<details>
  <summary><b> 1️⃣ Data Cleaning & Ethics (Click to expand)</b></summary>
  <br>
  <ul>
    <li><b>Forbidden Variables:</b> Identified and dropped columns that directly give away the diagnosis.</li>
    <li><b>Redundant Data:</b> Removed administrative columns like Patient IDs, Visit Dates, and Form Versions.</li>
  </ul>
</details>

<details>
  <summary><b> 2️⃣ Feature Engineering (Click to expand)</b></summary>
  <br>
  <ul>
    <li><b>Age Calculation:</b> Derived current age dynamically from visit and birth years.</li>
    <li><b>Categorical Encoding:</b> One-hot encoding for categorical features (Marital Status, Residency, etc.).</li>
    <li><b>Special Code Handling:</b> Replaced technical missingness codes (e.g., -4, 9, 99) with <code>NaN</code>.</li>
  </ul>
</details>

<details>
  <summary><b> 3️⃣ Smart Imputation (Click to expand)</b></summary>
  <br>
  <ul>
    <li><b>Zero Imputation:</b> Applied to behavioral history (e.g., smoking/alcohol) where missing implies "None".</li>
    <li><b>Median Imputation:</b> Applied to continuous demographics to maintain distribution integrity.</li>
  </ul>
</details>

---

## 📈 Model Performance

We benchmarked three major classifiers: **Random Forest**, **XGBoost**, and **LightGBM** (using `RandomizedSearchCV`). 

🏆 **XGBoost** emerged as the winning model:

> **Accuracy:** `~87.3%`
> 
> **F1-Score (Dementia):** `0.80`
> 
> **AUROC (Area Under Curve):** `~0.93`

<br>

### 🔑 Top 5 Predictive Features
1. `NACCDIED` (Death status)
2. `NACCLIVS` (Living situation)
3. `RESIDENC` (Type of residence)
4. `NACCPAFF` (Psychiatric symptoms)
5. `TELCOV` (Telephone coverage)

---

## 💻 Quick Start

Clone the repository and run the notebooks locally:

```bash
# 1. Clone the repo
git clone [https://github.com/usmaanimran/modelx_hackerthon_zypher.git](https://github.com/usmaanimran/modelx_hackerthon_zypher.git)

# 2. Install dependencies
pip install pandas numpy scikit-learn xgboost lightgbm matplotlib seaborn

# 3. Launch Jupyter
jupyter notebook
