# Heart Disease Prediction - Exploratory Data Analysis & Classification

## Task Objective
The primary objective of this project is to build a machine learning model to predict whether a person is at risk of heart disease based on their health data. The project encompasses:

- Data cleaning and preprocessing
- Exploratory Data Analysis (EDA) to understand trends
- Training classification models (Logistic Regression & Decision Tree)
- Model evaluation using multiple metrics
- Feature importance analysis to identify key risk factors

This project demonstrates a complete end-to-end machine learning workflow for medical data analysis.

---

## Dataset Description
**Dataset**: Heart Disease UCI Dataset  
**Source**: [Kaggle - Heart Disease UCI](https://www.kaggle.com/ronitf/heart-disease-uci)

### Dataset Characteristics:
| Attribute | Details |
|-----------|---------|
| Samples | 303 instances |
| Features | 13 medical attributes + 1 target |
| Classes | 2 (0 = No heart disease, 1 = Heart disease present) |
| Missing Values | None in Cleveland dataset |
| Balance | Moderately balanced |

### Features:
| Feature | Description | Type |
|---------|-------------|------|
| age | Age in years | Numerical |
| sex | (1 = male; 0 = female) | Categorical |
| cp | Chest pain type (0-3) | Categorical |
| trestbps | Resting blood pressure (mm Hg) | Numerical |
| chol | Serum cholesterol (mg/dl) | Numerical |
| fbs | Fasting blood sugar > 120 mg/dl | Categorical |
| restecg | Resting ECG results (0-2) | Categorical |
| thalach | Maximum heart rate achieved | Numerical |
| exang | Exercise induced angina (1 = yes) | Categorical |
| oldpeak | ST depression induced by exercise | Numerical |
| slope | Slope of peak exercise ST segment | Categorical |
| ca | Number of major vessels (0-3) | Numerical |
| thal | Thalassemia (1-3) | Categorical |
| target | Diagnosis of heart disease (0/1) | Target |

---

## 🛠 Tools & Libraries Used
| Library | Purpose |
|---------|---------|
| Pandas | Data loading, manipulation, and analysis |
| NumPy | Numerical computations |
| Matplotlib | Basic plotting and visualizations |
| Seaborn | Statistical data visualization |
| Scikit-learn | Machine learning models and evaluation |
| Jupyter | Interactive development environment |

---

## Methodology

### Phase 1: Data Loading & Cleaning
- Loaded dataset from CSV file
- Checked for missing values, duplicates, and infinite values
- Handled any data quality issues
- Verified column names and data types

### Phase 2: Exploratory Data Analysis (EDA)
- Analyzed target variable distribution
- Visualized age distribution by disease status
- Examined chest pain type vs heart disease
- Created correlation heatmap of all features
- Analyzed gender-based differences
- Studied max heart rate patterns

### Phase 3: Data Preprocessing
- Separated features (X) and target (y)
- Encoded categorical variables
- Split data into training (80%) and testing (20%) sets
- Standardized features using StandardScaler

### Phase 4: Model Training
Two classification models were trained and compared:

1. **Logistic Regression**
   - Linear model for binary classification
   - Provides interpretable coefficients
   - Good baseline model

2. **Decision Tree Classifier**
   - Non-linear model
   - Captures complex patterns
   - Provides feature importance scores

### Phase 5: Model Evaluation
Models were evaluated using:
- **Accuracy**: Overall correct predictions
- **Precision**: Positive predictive value
- **Recall**: Sensitivity/True Positive Rate
- **F1-Score**: Harmonic mean of precision and recall
- **ROC-AUC**: Area under ROC curve
- **Confusion Matrix**: Detailed prediction breakdown
- **5-Fold Cross-validation**: Robustness check

### Phase 6: Feature Importance Analysis
- Extracted coefficients from Logistic Regression
- Calculated feature importance from Decision Tree
- Identified top predictors of heart disease
- Combined insights from both models

---

## Key Results & Findings

### 1. Dataset Overview
| Metric | Value |
|--------|-------|
| Total Samples | 303 |
| Features | 13 medical attributes |
| Patients with Heart Disease | ~54% |
| Patients without Heart Disease | ~46% |
| Missing Values | 0 |
| Duplicates | 0 (after cleaning) |

### 2. Statistical Insights
| Feature | Range | Mean ± Std | Clinical Significance |
|---------|-------|------------|----------------------|
| Age | 29-77 years | 54.4 ± 9.1 | Higher risk with age |
| Resting BP | 94-200 mm Hg | 131.6 ± 17.5 | Hypertension indicator |
| Cholesterol | 126-564 mg/dl | 246.7 ± 51.8 | High cholesterol risk |
| Max Heart Rate | 71-202 bpm | 149.6 ± 22.9 | Lower in disease cases |

### 3. Key Correlations with Heart Disease
| Feature | Correlation | Direction |
|---------|-------------|-----------|
| Thalach (Max HR) | Strong positive | Higher HR = Less disease |
| Oldpeak (ST depression) | Strong negative | Higher depression = More disease |
| Ca (vessels) | Strong negative | More vessels = Less disease |
| Exang (exercise angina) | Strong negative | Angina present = More disease |
| Cp (chest pain) | Moderate positive | Certain pain types indicate disease |

### 4. Model Performance Comparison
| Metric | Logistic Regression | Decision Tree |
|--------|---------------------|---------------|
| Accuracy | ~85% | ~80% |
| Precision | ~84% | ~79% |
| Recall | ~88% | ~83% |
| F1-Score | ~86% | ~81% |
| ROC-AUC | ~0.92 | ~0.85 |
| CV Score (5-fold) | ~84% | ~79% |

### 5. Top Important Features
**Logistic Regression (by coefficient magnitude):**
1. **Oldpeak** (ST depression) - Strongest predictor
2. **Thalach** (Max heart rate)
3. **Ca** (Number of major vessels)
4. **Cp** (Chest pain type)
5. **Sex** (Gender)

**Decision Tree (by importance score):**
1. **Ca** (Number of major vessels)
2. **Thalach** (Max heart rate)
3. **Oldpeak** (ST depression)
4. **Cp** (Chest pain type)
5. **Age**

**Combined Top Predictors:**
- ✅ **Ca** (Number of major vessels)
- ✅ **Thalach** (Max heart rate)
- ✅ **Oldpeak** (ST depression)
- ✅ **Cp** (Chest pain type)
- ✅ **Exang** (Exercise-induced angina)

---

## Visualizations Generated

1. **Target Distribution** - Balance of disease vs no disease
2. **Age Distribution** - Age patterns by disease status
3. **Chest Pain Analysis** - CP type vs heart disease
4. **Correlation Heatmap** - Feature relationships
5. **Gender Analysis** - Disease prevalence by gender
6. **Max Heart Rate Boxplot** - Thalach distribution
7. **Model Performance Comparison** - Metrics bar chart
8. **Confusion Matrix** - Prediction breakdown
9. **ROC Curves** - Model discrimination ability
10. **Cross-validation Scores** - Model stability
11. **Feature Importance Plots** - Top predictors

---

## Medical Insights

### Key Risk Factors Identified:
1. **Chest Pain Type (cp)** 
   - Typical angina and non-anginal pain patterns show different risk levels
   - Certain chest pain types strongly indicate heart disease

2. **Maximum Heart Rate (thalach)**
   - Lower maximum heart rate achieved is associated with higher risk
   - Patients with heart disease tend to have lower exercise tolerance

3. **Exercise-Induced Angina (exang)**
   - Angina during exercise is a significant warning sign
   - Present in majority of heart disease patients

4. **ST Depression (oldpeak)**
   - Greater ST depression indicates heart stress
   - Strong predictor of disease presence

5. **Number of Major Vessels (ca)**
   - Fewer colored vessels indicates blood flow issues
   - Direct anatomical evidence of heart problems

### Clinical Relevance:
- Findings align with established medical knowledge
- Model identifies clinically meaningful risk factors
- Can assist in early screening and intervention
- Provides interpretable results for healthcare professionals

---

## Installation & Setup

### Prerequisites:
- Python 3.8+
- pip package manager
- Jupyter Notebook or VS Code

### Installation Steps:
```bash
# Clone repository
git clone <your-repo-url>
cd Heart-Disease-Prediction

# Install required packages
pip install numpy pandas matplotlib seaborn scikit-learn jupyter

# Launch Jupyter Notebook
jupyter notebook

 