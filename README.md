# course_completion_prediction
# ML Project: Predicting Course Completion (Moodle Platform)

## Problem Statement
In an online learning platform offering finance-related courses across multiple formats, it is important to identify learners who are at risk of not completing their courses.

This project aims to build a machine learning model to predict whether a learner will complete a course based on engagement, performance, and behavioral data. The goal is to enable proactive interventions to improve course completion rates.

---

## Dataset Description
A synthetic dataset was created to simulate real-world Moodle platform data.

### Features
- Demographics: Age, Country  
- Course Details: Course Type, Category, Price  
- Engagement: Time Spent, Login Frequency, Forum Posts  
- Performance: Quiz Score, Assignments Completed  
- Activity: Last Login, Video Completion %  
- Others: Device Type, Payment Type, Certificate Attempted  

###  Target Variable
- `course_completed`
  - 1 → Completed  
  - 0 → Not Completed  

---

##  Data Preprocessing
- Missing values handled (rows removed ~5%)  
- Duplicate records removed
- Unique column removed i.e. user_id
- Outliers detected using IQR and handled via capping  

---

##  Exploratory Data Analysis (EDA)
- Higher engagement → higher completion  
- Better performance → higher completion  
- Moderate correlation with target variable  

---

##  Feature Engineering
- One-Hot Encoding for categorical variables  
- Feature Scaling using StandardScaler  
- PCA applied to retain 95% variance  

---

##  Model Building
Models used:
- Logistic Regression  
- Decision Tree  
- Random Forest  

---

##  Model Evaluation

| Model | Accuracy | Recall (Class 1) |
|------|--------|----------------|
| Logistic Regression | **86.4%** | **0.81** |
| Decision Tree | 75% | 0.64 |
| Random Forest | 83.5% | 0.70 |

###  Final Model
**Logistic Regression** was selected as the final model due to:
- Highest accuracy  
- Better balance between precision and recall  
- More reliable performance across both classes  

---

##  Prediction Example

```python
Prediction = [0]
Probability = [[0.84, 0.16]]
