
# Obesity Level Prediction and Personalized Lifestyle Recommendations

A Machine Learning-based project that predicts an individual's obesity level using demographic, physical, dietary, and lifestyle information. The project also integrates Generative AI to provide personalized diet, exercise, and lifestyle recommendations.

## Project Overview

Obesity is influenced by several factors, including eating habits, physical activity, genetics, and lifestyle choices.

This project uses Machine Learning algorithms to classify individuals into seven obesity categories based on their personal and lifestyle information.

Five classification algorithms are compared, with Random Forest selected as the primary prediction model. Additionally, Google's Gemini Generative AI API is integrated to generate personalized lifestyle recommendations based on the predicted obesity level and user characteristics.

## Objectives

- Predict obesity levels using Machine Learning.
- Analyze demographic, dietary, physical, and lifestyle factors.
- Compare the performance of different classification algorithms.
- Implement Random Forest as the primary classifier.
- Calculate BMI as an additional feature.
- Generate personalized lifestyle recommendations using Generative AI.

## Dataset

The project uses the publicly available **Estimation of Obesity Levels Based on Eating Habits and Physical Condition in Individuals from Colombia, Peru and Mexico** dataset.

- Total Records: 2,111
- Original Attributes: 17
- Target Variable: `NObeyesdad`
- Prediction Categories: 7

### Input Features

| Feature | Description |
|---|---|
| Gender | Gender of the individual |
| Age | Age in years |
| Height | Height in meters |
| Weight | Weight in kilograms |
| family_history_with_overweight | Family history of overweight |
| FAVC | Frequent consumption of high-calorie food |
| FCVC | Frequency of vegetable consumption |
| NCP | Number of main meals |
| CAEC | Consumption of food between meals |
| SMOKE | Smoking status |
| CH2O | Daily water consumption |
| SCC | Monitoring calorie consumption |
| FAF | Frequency of physical activity |
| TUE | Time spent using technology |
| CALC | Alcohol consumption frequency |
| MTRANS | Main mode of transportation |

### BMI Calculation

BMI is calculated using height and weight and added as an additional feature.

BMI = Weight (kg) / Height (m)²

### Prediction Categories

1. Insufficient Weight
2. Normal Weight
3. Overweight Level I
4. Overweight Level II
5. Obesity Type I
6. Obesity Type II
7. Obesity Type III

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Google Gemini Generative AI API

## Machine Learning Algorithms

Five supervised classification algorithms were implemented and compared:

1. Random Forest Classifier
2. XGBoost Classifier
3. Gradient Boosting Classifier
4. Decision Tree Classifier
5. K-Nearest Neighbors (KNN)

Random Forest was selected as the primary classification model.

## Project Workflow

1. Dataset Loading and Exploration
2. Data Cleaning and Preprocessing
3. Duplicate Removal
4. Exploratory Data Analysis (EDA)
5. Categorical Feature Encoding
6. Correlation Analysis
7. BMI Feature Engineering
8. Train-Test Split (80:20)
9. Model Training and Comparison
10. Model Evaluation
11. Obesity Level Prediction
12. Gemini Generative AI Integration
13. Personalized Lifestyle Recommendations

## Model Performance

The following results were reported in the research paper using an 80:20 stratified train-test split.

| Algorithm | Training Accuracy | Testing Accuracy |
|---|---:|---:|
| Random Forest | 100.00% | 98.80% |
| XGBoost | 100.00% | 98.80% |
| Gradient Boosting | 100.00% | 98.33% |
| Decision Tree | 100.00% | 96.89% |
| KNN | 96.64% | 94.74% |

### Random Forest Classification Performance

| Metric | Result |
|---|---|
| Training Accuracy | 100.00% |
| Testing Accuracy | 98.80% |
| Evaluation | Classification Report and Confusion Matrix |

BMI was identified as the most influential feature in the Random Forest feature-importance analysis, followed by Weight and other physical and lifestyle variables.

## Generative AI Integration

Google Gemini Generative AI is integrated to provide personalized recommendations after the obesity prediction.

Based on the predicted obesity category and user information, the system generates:

- Health Assessment
- BMI Analysis
- Recommended Daily Calories
- Vegetarian Diet Plan
- Exercise Plan
- Foods to Avoid
- Lifestyle Changes
- Expected Improvement

The AI recommendation module uses the user's age, height, weight, BMI, dietary habits, physical activity, and other lifestyle information.

## Installation and Execution

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/obesity-prediction-classifier.git
```

### 2. Navigate to the Project Directory

```bash
cd obesity-prediction-classifier
```

### 3. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost google-generativeai
```

### 4. Add the Dataset

Place the obesity dataset CSV file in the project directory.

Update the dataset path in the Python script if necessary.

```python
df = pd.read_csv("ObesityDataSet_raw_and_data_sinthetic.csv")
```

### 5. Configure Gemini API

Set your Gemini API key as an environment variable instead of hardcoding it in the Python script.

```python
import os
import google.generativeai as genai

genai.configure(api_key=os.environ["GEMINI_API_KEY"])
```

### 6. Run the Project

```bash
python ml_project.py
```

The program trains and evaluates the classification models, accepts user information, predicts the obesity category, and generates lifestyle recommendations when the Gemini API is configured.

## Research Paper

**Title:** Obesity Level Prediction and Personalized Lifestyle Recommendations Using Random Forest and Generative AI

**Authors:**
- Romil Atmaramani
- Meha Goswami

**Department:** Computer Science and Engineering, Indus University, Ahmedabad, India.

The research paper covers the dataset, methodology, system architecture, model comparison, experimental results, feature importance, limitations, and conclusion.

## Limitations and Future Improvements

- Evaluation is based on a single train-test split.
- Cross-validation and external dataset validation are required for stronger generalization assessment.
- Hyperparameter optimization can be explored.
- Generative AI recommendations require professional review and clinical validation.
- The model should be tested on more diverse populations.

## Disclaimer

This project is developed for academic, educational, and research purposes only. It is not a clinically validated diagnostic system and should not replace professional medical advice.

---

**Developed by Romil Atmaramani and Meha Goswami**  
Department of Computer Science and Engineering  
Indus University, Ahmedabad, India.
