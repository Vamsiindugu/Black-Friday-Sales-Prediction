
# 🛍️ Black Friday Sales Prediction  

![Python Version](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Libraries](https://img.shields.io/badge/Libraries-LightGBM%20%7C%20XGBoost%20%7C%20Scikit--Learn-orange.svg)
![Kaggle](https://img.shields.io/badge/Dataset-Kaggle-blue.svg)

An elite implementation of a **gradient boosting pipeline** to predict customer purchase amounts from the [Black Friday Sales dataset](https://www.kaggle.com/datasets/sdolezel/black-friday). This project exemplifies how **cutting-edge feature engineering**, **optimized data pipelines**, and **state-of-the-art machine learning models** drive superior accuracy over baseline models ✅.

---

## 📚 Table of Contents

- [📌 Project Overview](#-project-overview)
- [📂 Dataset Information](#-dataset-information)
- [⚙️ Methodology & Implementation](#️-methodology--implementation)
  - [🔧 Data Preparation & Optimization](#-data-preparation--optimization)
  - [💡 Feature Engineering (The Core Strategy)](#-feature-engineering-the-core-strategy)
  - [🎯 Modeling & Training Strategy](#-modeling--training-strategy)
- [📈 Results & Performance](#-results--performance)
- [🚀 Getting Started](#-getting-started)
  - [📋 Prerequisites](#-prerequisites)
  - [🔗 Installation](#-installation)
  - [📓 Running the Notebook](#-running-the-notebook)
- [🛠️ Usage](#️-usage)
- [🤝 Contributing](#-contributing)

---

## 📌 Project Overview

This repository tackles the Black Friday sales regression problem using **advanced ensemble models** and **domain-inspired features** to accurately predict customer purchase behavior.

🔍 **Objective**: Build a high-accuracy regressor for predicting the `Purchase` amount based on customer demographics and product metadata.

### 💎 Highlights

- 🧠 Integrates **behavioral features** from ID columns often discarded in traditional pipelines.
- ⚡ Powered by **LightGBM**, optimized with early stopping, memory-efficient design, and robust validation.
- 📉 Achieves a **~13% RMSE reduction** over XGBoost baseline models from benchmark notebooks.

---

## 📂 Dataset Information

> Source: [Kaggle - Black Friday Sales](https://www.kaggle.com/datasets/sdolezel/black-friday)

| Feature Type | Columns |
|--------------|---------|
| **Identifiers** | `User_ID`, `Product_ID` |
| **Demographics** | `Gender`, `Age`, `Occupation`, `Marital_Status` |
| **Location** | `City_Category`, `Stay_In_Current_City_Years` |
| **Product Categories** | `Product_Category_1`, `Product_Category_2`, `Product_Category_3` |
| **Target Variable** | `Purchase` (Total purchase amount) |

---

## ⚙️ Methodology & Implementation

A well-engineered, end-to-end pipeline designed for high predictive accuracy and scalability.

### 🔧 Data Preparation & Optimization

- ✅ **Memory-efficient Loading**: Custom `dtype` assignments reduced memory usage by **~57%**, boosting overall pipeline performance.
- ✅ **Fast EDA**: Exploratory analysis executed on stratified samples to balance performance with insight.
- ✅ **Correct Encoding**:
  - `City_Category`: One-Hot Encoded (nominal)
  - Remaining categoricals: `LabelEncoded` for compatibility with tree models

---

### 💡 Feature Engineering (The Core Strategy)

The game-changer for this model. Instead of dropping high-cardinality IDs, we extracted **aggregate behavioral indicators**:

| Feature | Description |
|--------|-------------|
| `User_Mean_Purchase` | Mean purchase value per user |
| `Product_Mean_Purchase` | Average spend per product |
| `Occupation_Mean_Purchase` | Avg. purchase behavior per occupation class |

> These features introduce **latent signals**, helping the model capture purchasing trends tied to customer habits and product pricing tiers.

---

### 🎯 Modeling & Training Strategy

- 🚀 **Model**: `LightGBM Regressor` — renowned for handling large, tabular datasets efficiently.
- 🔍 **Validation Split**:
  - Training: 60%
  - Validation: 20%
  - Testing: 20%
- 🛑 **Early Stopping**:
  - Up to 5000 estimators trained
  - Stops if validation RMSE doesn’t improve after 50 rounds

> Feature importance plots were used post-training to confirm the effectiveness of the engineered features.

---

## 📈 Results & Performance

The model outperformed strong benchmarks by a considerable margin:

### 📊 Final Evaluation

| Metric | XGBoost Baseline | **Our LightGBM Model** | 🏆 Outcome |
|--------|------------------|-------------------------|------------|
| RMSE   | 2879.32           | **2505.71**             | ✅ **13% Lower Error** |
| R²     | 0.665             | **0.756**               | ✅ **13.7% Gain**      |

```text
--- Final Model Performance ---
R² Score: 0.75628
RMSE:     2505.71
```

---

## 🚀 Getting Started

Clone the repository and run the pipeline on your machine in minutes.

### 📋 Prerequisites

- Python 3.9+
- Jupyter Lab
- pip (Python Package Installer)

### 🔗 Installation

```bash
# 1. Clone the repo
git clone https://github.com/your-username/black-friday-sales-prediction.git
cd black-friday-sales-prediction

# 2. (Optional but Recommended) Set up a virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt
```

> Or install manually:
```bash
pip install pandas scikit-learn matplotlib seaborn jupyterlab xgboost lightgbm
```

---

### 📓 Running the Notebook

1. Launch Jupyter Lab:
   ```bash
   jupyter lab
   ```
2. Open the notebook file.
3. Execute all cells to replicate results.

---

## 🛠️ Usage

This pipeline can be adapted for:

- 🎯 **Large-scale regression tasks**
- 🧠 **Advanced ML training for tabular data**
- 💼 **Real-world retail analytics**
- 🚀 **Production-ready model deployment (via `joblib` or `pickle`)**

---

## 🤝 Contributing

Contributions and improvements are welcome 🙌

1. Fork the project
2. Create a feature branch  
   ```bash
   git checkout -b feature/my-new-feature
   ```
3. Commit your changes  
   ```bash
   git commit -m 'Add my new feature'
   ```
4. Push the branch  
   ```bash
   git push origin feature/my-new-feature
   ```
5. Open a Pull Request

---

