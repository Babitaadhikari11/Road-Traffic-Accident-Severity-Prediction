
# 🚦 Road Traffic Accident Severity Prediction

## 📌 Project Overview

This project focuses on predicting the severity of road traffic accidents using Machine Learning techniques.

The main objective is to analyze accident-related factors and classify accident severity into three categories:

- Fatal injury
- Serious Injury
- Slight Injury

The project covers data understanding, exploratory data analysis, preprocessing, feature engineering, model training, hyperparameter tuning, and model evaluation.

## 📊 Dataset

The dataset contains 8,210 road traffic accident records.

**Target Variable:** `Accident_severity`

The dataset contains information related to:
- Driver characteristics
- Vehicle information
- Road conditions
- Weather conditions
- Accident circumstances
- Time-related factors

The target variable is imbalanced, with the following distribution:

| Accident Severity | Records |
|---|---:|
| Slight Injury | 7,082 |
| Serious Injury | 1,046 |
| Fatal injury | 82 |

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Jupyter Notebook
- Joblib

## 🔍 Project Workflow

### 1. Data Understanding
- Loaded and explored the dataset.
- Examined data types and missing values.
- Analyzed the target variable distribution.

### 2. Exploratory Data Analysis (EDA)
- Visualized accident severity distribution.
- Explored relationships between accident severity and other features.
- Identified class imbalance in the dataset.

### 3. Data Preprocessing
- Handled missing values.
- Prepared categorical and numerical features.
- Removed irrelevant and potentially leakage-causing features.

### 4. Feature Engineering
Created additional features to improve the dataset representation:

- `Hour`
- `Time_of_day`
- `Is_weekend`

### 5. Model Training

Trained three machine learning algorithms:

1. Logistic Regression
2. Random Forest
3. XGBoost

Used an 80/20 stratified train-test split.

### 6. Class Imbalance Handling

Applied balanced class weights and sample weights to improve the identification of minority accident severity classes.

### 7. Hyperparameter Tuning

Used:
- GridSearchCV for Logistic Regression
- RandomizedSearchCV for Random Forest
- RandomizedSearchCV for XGBoost
- Stratified 5-Fold Cross-Validation

Macro F1-score was used as the primary tuning metric.

## 📈 Model Performance

The following results were obtained on the test dataset:

| Model | Accuracy | Macro F1 |
|---|---:|---:|
| Logistic Regression | 52.31% | 0.3083 |
| Tuned Logistic Regression | 51.71% | 0.3037 |
| Random Forest | 86.24% | 0.3087 |
| Tuned Random Forest | 73.69% | 0.4104 |
| XGBoost | 86.18% | 0.4243 |
| **Weighted XGBoost** | **83.25%** | **0.4927** |
| Tuned Weighted XGBoost | 64.86% | 0.3764 |

## 🏆 Selected Model

**Weighted XGBoost** was selected as the leading model candidate because it achieved the highest Macro F1-score among the evaluated configurations.

### Performance

- Accuracy: 83.25%
- Macro F1-score: 0.4927
- Fatal Injury Recall: 24%
- Serious Injury Recall: 20%
- Slight Injury Recall: 93%

Although the model achieved relatively high overall accuracy, identifying severe accidents remains challenging because of class imbalance.

## 💾 Model Saving

The selected Weighted XGBoost model was saved using Joblib.

The saved package contains:

- Trained Weighted XGBoost model
- Feature column names
- Label encoder

Saved model:

`models/traffic_severity_model.pkl`

The saved model can be loaded without retraining. New input data must undergo the same feature engineering and categorical encoding used during training.

## 📁 Project Structure

```text
Road-Traffic-Accident-Severity-Prediction/
│
├── data/
│   └── feature_engineered_traffic.csv
│
├── notebooks/
│   ├── 01_Data_Understanding.ipynb
│   ├── 02_EDA.ipynb
│   ├── 03_Data_Preprocessing.ipynb
│   ├── 04_Feature_Engineering.ipynb
│   └── 05_Models.ipynb
│
├── models/
│   └── traffic_severity_model.pkl
│
└── README.md
```

## ⚠️ Limitations

- The dataset is highly imbalanced.
- Fatal injury cases are underrepresented.
- The selected model has limited recall for Fatal and Serious Injury classes.
- Hyperparameter tuning did not consistently improve test performance.
- Model comparison and selection used the test dataset, so the reported results should be treated as exploratory rather than an unbiased final performance estimate.
- Further validation is required before any real-world use.

## 🚀 Future Improvements

- Explore additional class imbalance handling techniques.
- Improve recall for severe accident categories.
- Use a separate final holdout dataset for unbiased evaluation.
- Develop a reusable preprocessing pipeline.
- Build a simple prediction interface.
- Evaluate the model on additional accident datasets.

## 📝 Conclusion

This project demonstrates the application of machine learning algorithms to road traffic accident severity prediction.

Logistic Regression, Random Forest, and XGBoost were trained and compared using multiple evaluation metrics.

Weighted XGBoost achieved the highest Macro F1-score of 0.4927 among the evaluated models.

The project highlights the importance of class imbalance handling, appropriate evaluation metrics, and understanding the trade-offs between overall accuracy and minority-class detection.

## 👩‍💻 Author

**Babita Adhikari**


GitHub: https://github.com/Babitaadhikari11

LinkedIn: https://www.linkedin.com/in/babita-adhikari-426494425/

---


