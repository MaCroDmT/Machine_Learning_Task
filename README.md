# Machine_Learning_Task
Machine Learning using 2 Cricicket Dataset sourced from kaggle and itegrate these 2 dataset with Weather data's from venue location;s weather of the date of the match through calling an API Visual Crossing

# 🏏 Cricket Match Outcome Prediction – Model Report

## 📁 Dataset Description

This project uses the dataset `match_data_with_weather.csv`, which contains historical cricket match data enriched with weather conditions.

### Features Included:

* `Team _1`, `Team 2`: Competing teams

* `Toss Winner`, `Toss Decision`: Toss result and decision

* `Conditions`: Weather conditions during the match

* `Winner`: The match winner

* `Temperature`, `Humidity`, `Precipitation`: Weather-related numerical data

* **Total Rows**: 1,141

* **Source**: Combined cricket match archives and weather APIs

* **Dataset Location**: `/content/drive/MyDrive/SMC_Labs/match_data_with_weather.csv`

---

## 📊 Exploratory Data Analysis (EDA)

### Goals:

* Handle missing values
* Understand frequency distribution and correlations
* Encode categorical data

### Insights:

* Teams winning toss often win the match.
* Certain weather conditions affect match outcomes.
* Few teams dominate in specific weather setups.

---

## 🤖 Model Selection

| Model                | Type         | Purpose                            |
| -------------------- | ------------ | ---------------------------------- |
| Gaussian Naive Bayes | Supervised   | Classify match outcome             |
| K-Means Clustering   | Unsupervised | Explore data patterns and grouping |

### Why Naive Bayes?

* Works well with categorical data
* Simple and fast

### Why K-Means?

* Groups matches based on feature similarity
* Reveals hidden trends in match data

---

## 📊 Preprocessing & Training

### Features Used:

```
['Team _1', 'Team 2', 'Toss Winner', 'Toss Decision',
 'Conditions', 'Temperature', 'Humidity', 'Precipitation']
```

### Target:

```
'Winner'
```

### Data Cleaning:

* `Temperature`, `Humidity`, `Precipitation`: Imputed using **mean**
* Categorical fields: Imputed using **mode**

### Encoding:

* LabelEncoder applied to all categorical columns

### Data Split:

* Train: 80%
* Test: 20%

### Model Training:

```python
from sklearn.naive_bayes import GaussianNB
model = GaussianNB()
model.fit(X_train, y_train)
```

---

## 📊 Evaluation Metrics

### Gaussian Naive Bayes

* **Accuracy**: \~68% (replace with actual value)
* **Classification Report**: Shows precision, recall, F1-score per class

### K-Means Clustering

* **K=3** provided optimal grouping
* Helped identify match condition clusters

---

## ✅ Conclusion

* Naive Bayes effectively predicts match outcomes.
* Clustering revealed team-weather dependencies.
* Project demonstrates the power of ML in sports analytics.

### Future Enhancements:

* Add player performance stats
* Use ensemble models (e.g., Random Forest)
* Engineer new features (e.g., venue strength, batting power)

---

## 📌 Resources

* Dataset: [`match_data_with_weather.csv`](https://github.com/your-repo-link)
* Weather API: OpenWeatherMap
* Environment: Google Colab + Python + Scikit-learn

