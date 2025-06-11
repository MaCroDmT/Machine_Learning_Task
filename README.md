---

# 🏏 Cricket Match Outcome Prediction using Machine Learning

## 📌 Project Overview

In the world of cricket, predicting match outcomes is both exciting and challenging. This project aims to build a machine learning model that predicts the outcome of cricket matches using structured match metadata, ball-by-ball data, and real-world environmental conditions like weather. It simulates a real-world sports analytics use case that could benefit fans, broadcasters, and strategists alike.

---

## 🎯 Objective

The main objective is to develop a predictive model that can determine the result of a cricket match using available features prior to or during the match. This includes comprehensive data preprocessing, exploratory analysis, feature engineering, model selection, and performance evaluation.

---

## 🧰 Tools & Technologies

| Tool/Library         | Purpose                                 |
| -------------------- | --------------------------------------- |
| Python               | Core programming language               |
| Pandas               | Data preprocessing and manipulation     |
| NumPy                | Numerical operations                    |
| Scikit-learn         | ML models, preprocessing, evaluation    |
| Matplotlib / Seaborn | Data visualization during EDA           |
| Google Colab         | Notebook environment for implementation |
| Google Drive         | Dataset access and storage              |

---

## 📁 Dataset Description

This project uses two primary datasets:

1. **`match_info.csv`** – Contains structured metadata for each match, such as city, date, teams, toss results, venue, and final outcome.
2. **`ball_by_ball_data.csv`** – Provides granular delivery-level insights like runs scored, wicket types, and player activity.

To enhance prediction accuracy, weather data was integrated using the **Visual Crossing Weather API**, fetching temperature, humidity, precipitation, and general weather conditions for each match. This enriched dataset, containing 1,141 usable records, was saved as `match_data_with_weather.xlsx` and used for training.

---

## 📊 Exploratory Data Analysis (EDA)

The EDA phase involved:

* Merging match-level and ball-by-ball data to provide context and compute features like **team average runs**.
* Integrating **weather features** (temperature, humidity, etc.).
* Selecting relevant columns: teams, toss outcomes, weather conditions, and final match result.
* Handling missing values:

  * **Numerical features** → filled using mean imputation.
  * **Categorical features** → filled using mode.
* Label encoding categorical features and applying **MinMax Scaling** for normalization.

---

## 🧠 Model Selection Criteria

Models were chosen based on their:

* Compatibility with categorical & numerical data
* Interpretability and speed
* Performance on small datasets

### Evaluated Models:

* **Naive Bayes** (fast, interpretable baseline)
* **Decision Tree & Random Forest** (handle non-linearity, better accuracy)
* **Logistic Regression, SVM, KNN** (as benchmarks)
* **XGBoost** (best performance with feature-rich, structured data)

> Deep learning models were avoided due to the relatively small dataset size.

---

## 🏗️ Model Architecture & Training

* Merged datasets and engineered features like `Team1_AvgRuns`, `Team2_AvgRuns`
* Integrated weather data (API-based) and normalized the dataset
* Trained multiple models using `train_test_split` (80% train / 20% test)
* Final models trained:

  * **Naive Bayes**: Simple, quick, interpretable
  * **XGBoost**: Best overall performance with feature importance insights

---

## 🧪 Evaluation Metrics

Performance was assessed using:

* **Accuracy**
* **Precision, Recall, F1-score** (from classification report)

### 📉 Baseline Models:

* **Random Forest (pre-feature engineering)**: 55% accuracy
* **Random Forest (post-feature engineering)**: 60% accuracy
* **Naive Bayes**: Only \~20% accuracy (poor generalization)

### 🌦️ With Weather Data:

| Model               | Accuracy  | Macro F1-Score | Remarks                              |
| ------------------- | --------- | -------------- | ------------------------------------ |
| Logistic Regression | 20.2%     | 0.07           | Poor across all teams                |
| Decision Tree       | 53.5%     | 0.33           | Decent on top teams                  |
| KNN                 | 24.8%     | 0.16           | Poor generalization                  |
| SVM                 | 26.4%     | 0.15           | Underfitting visible                 |
| **XGBoost**         | **62.8%** | **\~0.60**     | ✅ Best performer, robust predictions |

---

## 📈 Key Insights

* **Venue** played a critical role in match outcomes.
* **Weather conditions** (especially precipitation and humidity) showed noticeable influence.
* Feature engineering and dataset enrichment had a **direct positive impact** on accuracy.

---

## 🚀 Future Work

* Improve class balance to enhance predictions for lesser-known teams.
* Incorporate player-level statistics for more granular modeling.
* Experiment with time-series models if ball-by-ball sequences are retained.

---

## 📂 Project Structure

```
cricket-match-outcome-prediction/
├── match_info.csv
├── ball_by_ball_data.csv
├── match_data_with_weather.xlsx
├── notebooks/
│   └── model_training.ipynb
├── visuals/
│   └── eda_charts.png
├── README.md
└── requirements.txt
```

---

## 🤝 Acknowledgements

* Visual Crossing for weather data API.
* Scikit-learn, Pandas, and Matplotlib communities for excellent documentation.
* SMC Labs BD for the case study and challenge dataset.

---

Feel free to **fork**, **clone**, or **star** this project if you found it useful or want to build upon it!

---

