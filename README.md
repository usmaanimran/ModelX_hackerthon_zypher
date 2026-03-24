<h1 align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Orbitron&weight=700&size=40&pause=1000&color=00FF99&center=true&vCenter=true&width=800&lines=Dementia+Prediction+AI;ModelX+Hackathon;Engineered+By+TeamZypher" alt="Typing SVG" />
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=Jupyter&logoColor=white" alt="Jupyter"/>
  <img src="https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn"/>
  <img src="https://img.shields.io/badge/XGBoost-17A8F5?style=for-the-badge&logo=xgboost&logoColor=white" alt="XGBoost"/>
  <img src="https://img.shields.io/badge/LightGBM-ff69b4?style=for-the-badge&logo=Databricks&logoColor=white" alt="LightGBM"/>
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge" alt="Status"/>
</p>

<p align="center">
  <em>An advanced machine learning pipeline for predicting the likelihood of dementia, built with a strict focus on ethical feature selection, data privacy, and optimized gradient boosting.</em>
</p>

---

## 👥 The Zypher Core

<table align="center">
  <tr>
    <td align="center">
      <img src="https://ui-avatars.com/api/?name=Usmaan+Imran&background=0D8ABC&color=fff&rounded=true" width="80" alt="Usmaan"/><br>
      <b>Usmaan Imran</b><br><sub>Machine Learning, Model Optimization, Analytics</sub>
    </td>
    <td align="center">
      <img src="https://ui-avatars.com/api/?name=Zaidh&background=0D8ABC&color=fff&rounded=true" width="80" alt="Zaidh"/><br>
      <b>Zaidh</b><br><sub>Data Processing</sub>
    </td>
    <td align="center">
      <img src="https://ui-avatars.com/api/?name=Thasreef&background=0D8ABC&color=fff&rounded=true" width="80" alt="Thasreef"/><br>
      <b>Thasreef</b><br><sub>Data Processing</sub>
    </td>
  
  </tr>
</table>

---

## 🧪 Try It Yourself: Dataset & Challenge

Want to test your own models against our dataset or see the original hackathon challenge parameters? We have open-sourced the challenge materials for the community!

> 🔗 **[Access the Dataset & Challenge Files Here (Google Drive)](https://drive.google.com/drive/folders/1c8T8Nw1m0qHT6sd58bJFwF6qDB3GiQWM)**

**Instructions to run locally:**
1. Download the `.csv` dataset from the Drive link above.
2. Place the dataset in the root folder of this cloned repository.
3. Run the Jupyter Notebooks to see our data cleaning and XGBoost pipeline in action.

---

## 🧠 Project Architecture & Ethical AI

<blockquote>
  <b>🛡️ The Ethical AI Mandate</b><br>
  Over 900 "forbidden" medical variables were intentionally stripped from this dataset. Why? To prevent data leakage and ensure the model acts as a genuine early-warning screening aid based on demographics and lifestyle, rather than simply mimicking direct clinical tests.
</blockquote>

<details>
  <summary><b> 1️⃣ Data Cleaning & Ethics (Click to expand)</b></summary>
  <br>
  <ul>
    <li><b>Forbidden Variables:</b> Identified and dropped columns that directly give away the diagnosis (e.g., direct cognitive test scores).</li>
    <li><b>Redundant Data:</b> Removed administrative noise like Patient IDs, Visit Dates, and internal Form Versions.</li>
  </ul>
</details>

<details>
  <summary><b> 2️⃣ Feature Engineering (Click to expand)</b></summary>
  <br>
  <ul>
    <li><b>Dynamic Age:</b> Derived current age mathematically from visit and birth years.</li>
    <li><b>Categorical Encoding:</b> One-hot encoding applied to features like Marital Status and Residency.</li>
    <li><b>Anomaly Correction:</b> Replaced technical missingness codes (e.g., <code>-4</code>, <code>9</code>, <code>99</code>, <code>9999</code>) with NumPy's <code>NaN</code>.</li>
  </ul>
</details>

<details>
  <summary><b> 3️⃣ Smart Imputation Protocol (Click to expand)</b></summary>
  <br>
  <ul>
    <li><b>Zero Imputation:</b> Applied to behavioral history (smoking/alcohol) where a missing value logically implies "None" or "Never".</li>
    <li><b>Median Imputation:</b> Applied to continuous demographics to maintain overall statistical distribution integrity.</li>
  </ul>
</details>

---

## 📊 Model Performance Matrix

We rigorously benchmarked three major classifiers: **Random Forest**, **XGBoost**, and **LightGBM**. Extensive hyperparameter tuning was conducted using `RandomizedSearchCV`. 

🏆 **XGBoost (Optimized)** emerged as the champion model:

| Metric | Performance | Status |
| :--- | :---: | :---: |
| **Accuracy** | `87.33%` | 🟢 Excellent |
| **F1-Score (Class 0)** | `0.91` | 🟢 Excellent |
| **F1-Score (Class 1)** | `0.80` | 🟡 Strong |
| **AUROC** | `0.9293` | 🟢 Excellent |

<br>

### 🔑 Top 5 Predictive Features
Based on our XGBoost feature importance analysis, the following variables carry the most predictive weight:
1. `NACCDIED` *(Death status)*
2. `NACCLIVS` *(Living situation)*
3. `RESIDENC` *(Type of residence)*
4. `NACCPAFF` *(Psychiatric symptoms)*
5. `TELCOV` *(Telephone coverage / Accessibility)*

---

## 💻 Quick Start Guide

```bash
# 1. Clone the Zypher repository
git clone [https://github.com/usmaanimran/modelx_hackerthon_zypher.git](https://github.com/usmaanimran/modelx_hackerthon_zypher.git)
cd modelx_hackerthon_zypher

# 2. Install required dependencies
pip install pandas numpy scikit-learn xgboost lightgbm matplotlib seaborn

# 3. Download the dataset from the Google Drive link and place it in the folder

# 4. Launch Jupyter Notebook
jupyter notebook
