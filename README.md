# Predicting Type II Diabetes Risk Using Socio-Economic & Behavioral Factors

## Project Overview

This project explores the viability of predicting Type II Diabetes using non-clinical data, focusing on socio-economic, demographic, and behavioral variables. Traditional diagnostic models often rely heavily on clinical measurements, but this analysis investigates the predictive power of lifestyle and environmental factors. The primary dataset used is the **2023 Behavioral Risk Factor Surveillance System (BRFSS)** survey, a comprehensive health survey conducted by the Centers for Disease Control and Prevention (CDC).

The project workflow includes extensive data preprocessing, feature engineering, and the development and evaluation of four distinct machine learning models: Logistic Regression, Random Forest, XGBoost, and a Dense Neural Network. The findings demonstrate that a Dense Neural Network can achieve a notable F1-score of 0.57 for the diabetic class, highlighting the significant influence of non-clinical factors in assessing diabetes risk.

The analysis is detailed in the following notebooks:
1.  `EDA_and_Preprocessing.ipynb`: Contains the full exploratory data analysis, data cleaning, and preprocessing steps.
2.  `Modelling.ipynb`: Contains the implementation and evaluation of all machine learning models.

---

## 📊 Data Sourcing

The dataset for this project is the **2023 BRFSS Landline and Cell Phone Data**, sourced directly from the [CDC's official website](https://www.cdc.gov/brfss/annual_data/annual_2023.html).

* **File:** `LLCP2023.XPT`
* **Description:** This is a large, nationwide dataset collected via telephone surveys of U.S. residents about their health-related risk behaviors, chronic health conditions, and use of preventive services.
* **Size:** The dataset is substantial and is stored in this repository using **Git Large File Storage (LFS)**.

---

## ⚙️ Project Workflow

### 1. Data Preprocessing & Cleaning

The raw BRFSS data required significant preprocessing to be suitable for machine learning. Key steps included:
* **Manual Encoding:** Survey responses are categorical and were manually encoded into numerical formats based on the official BRFSS codebook.
* **Handling Missing Values:** Missing or refused-to-answer entries (coded as 7, 9, etc.) were identified and imputed using appropriate strategies.
* **Feature Selection:** A subset of relevant socio-economic and behavioral variables was selected for the analysis, excluding most direct clinical indicators.
* **Class Imbalance:** The dataset exhibited a significant class imbalance between diabetic and non-diabetic respondents. This was addressed using the **Synthetic Minority Over-sampling Technique (SMOTE)** to create a more balanced dataset for model training, preventing model bias towards the majority class.

### 2. Feature Extraction & Engineering

The core of this project was to focus on non-clinical predictors. The features used for modeling were extracted from the cleaned dataset and include variables related to:
* **Demographics:** Age, Marital Status, Education Level, Employment Status
* **Lifestyle & Behavior:** Smoking Habits, Physical Activity, General Health Perception
* **Economic Stability:** Income Level, Home Ownership
* **Physical Attributes:** Body Mass Index (BMI), calculated from `WEIGHT2` and `HEIGHT3` variables.

### 3. Modeling & Evaluation

Four different classification models were built and trained on the preprocessed, SMOTE-balanced data to predict the likelihood of a respondent having Type II Diabetes.

1.  **Logistic Regression:** A baseline model to establish initial performance.
2.  **Random Forest:** An ensemble model to capture non-linear relationships.
3.  **XGBoost:** A gradient-boosted trees model known for its high performance.
4.  **Dense Neural Network:** A deep learning model built with TensorFlow/Keras to identify complex patterns in the data.

Each model was evaluated based on standard classification metrics, with a particular focus on the **F1-Score** for the minority (diabetic) class due to the original class imbalance.

---

## 📈 Results

The Dense Neural Network emerged as the best-performing model, achieving an **F1-score of 0.57** for the diabetic class. This result is significant as it demonstrates that non-clinical factors alone hold considerable predictive power for assessing Type II Diabetes risk. The model's success underscores the importance of considering social determinants of health in predictive public health initiatives.
