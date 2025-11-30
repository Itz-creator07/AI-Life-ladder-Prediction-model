# 🧠 AI Life Ladder Prediction Model

A machine learning project that predicts **Life Ladder scores** (self-reported well-being) based on socio-economic and political indicators from the **World Happiness Report**.

---

## 📊 Project Overview

### What Does This Project Do?

This model predicts **how happy people are in a country** based on factors like:
- 💰 GDP per capita
- 👥 Social support
- 🏥 Life expectancy
- 🗳️ Freedom to make life choices
- 💝 Generosity
- ⚖️ Corruption perceptions

### Why Is This Important?

Understanding well-being drivers helps:
- **Governments**: Evaluate policy effectiveness
- **Organizations**: Allocate resources to areas with low well-being
- **Researchers**: Understand complex relationships between economics, health, and happiness

---

## 🎯 Problem Statement

**Type**: Supervised Learning - Regression
**Target Variable**: Life Ladder score (continuous value from 0-10)
**Dataset**: World Happiness Report 2018
**Model**: Random Forest Regressor with hyperparameter tuning

---

## 📁 Dataset

**Source**: World Happiness Report (WHR2018Chapter2OnlineData.csv)

**Features** (16 total after cleaning):
- Log GDP per capita
- Social support
- Healthy life expectancy at birth
- Freedom to make life choices
- Generosity
- Perceptions of corruption
- Positive/Negative affect
- Confidence in national government
- Democratic Quality
- Delivery Quality
- GINI index metrics

**Size**: 1,562 country-year observations

---

## 🚀 Quick Start

### Prerequisites

- Python 3.7+
- Jupyter Notebook

### Installation

```bash
# Clone the repository
git clone https://github.com/Itz-creator07/AI-Life-ladder-Prediction-model.git
cd AI-Life-ladder-Prediction-model

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook "ML_Final_Project .ipynb"
```

---

## 🛠️ Methodology

### 1. Data Preparation
- **Missing values**: Dropped rows with missing Life Ladder scores; filled others with 0
- **Feature selection**: Used Random Forest feature importance to select top 5 features
- **Feature scaling**: StandardScaler for numerical features
- **Train/Val/Test split**: 64% / 16% / 20%

### 2. Model Selection
- **Algorithm**: Random Forest Regressor
- **Reason**: Handles non-linear relationships, robust to outliers, provides feature importance

### 3. Hyperparameter Tuning
- **Method**: GridSearchCV with 5-fold cross-validation
- **Parameters tuned**:
  - `n_estimators`: [100, 200, 300]
  - `max_depth`: [None, 5, 10]
  - `min_samples_split`: [2, 5, 10]
  - `min_samples_leaf`: [1, 5, 10]

### 4. Evaluation Metrics
- Mean Squared Error (MSE)
- Mean Absolute Error (MAE)
- R-squared (R²)

---

## 📈 Results

### Model Performance

| Metric | Training Set | Validation Set | Test Set |
|--------|-------------|----------------|----------|
| **MSE** | ~0.15 | ~0.35 | ~0.40 |
| **MAE** | ~0.30 | ~0.45 | ~0.50 |
| **R²** | ~0.95 | ~0.85 | ~0.82 |

### Top 5 Most Important Features

1. **Log GDP per capita** (~35% importance)
2. **Social support** (~25% importance)
3. **Healthy life expectancy** (~20% importance)
4. **Freedom to make life choices** (~12% importance)
5. **Perceptions of corruption** (~8% importance)

---

## 📂 Project Structure

```
AI-Life-ladder-Prediction-model/
├── ML_Final_Project .ipynb    # Main Jupyter notebook
├── README.md                    # This file
├── requirements.txt             # Python dependencies
└── data/                        # Dataset folder (add your data here)
    └── WHR2018Chapter2OnlineData.csv
```

---

## 🔍 Key Insights

1. **Economic factors** (GDP) are the strongest predictor of well-being
2. **Social support** is nearly as important as economics
3. **Health** (life expectancy) significantly impacts happiness
4. **Governance** (corruption, freedom) plays a meaningful role
5. Model achieves **82% R² on test data**, indicating strong predictive power

---

## 🧪 Future Improvements

- [ ] Test additional models (XGBoost, Gradient Boosting, Neural Networks)
- [ ] Implement feature engineering (interaction terms, polynomial features)
- [ ] Add time-series analysis for trend prediction
- [ ] Deploy model as a web app using Flask/Streamlit
- [ ] Create visualization dashboard for predictions

---

## 📚 References

- [World Happiness Report](https://worldhappiness.report/)
- [Scikit-learn Documentation](https://scikit-learn.org/)
- [Random Forest Regression](https://scikit-learn.org/stable/modules/ensemble.html#forest)

---

## 👨‍💻 Author

**Itzalen Lopez**
GitHub: [@Itz-creator07](https://github.com/Itz-creator07)

---

## 📄 License

This project is for educational purposes.

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## ⭐ Acknowledgments

- World Happiness Report team for the dataset
- AI4ALL program for the educational foundation
- Scikit-learn community for excellent ML tools
