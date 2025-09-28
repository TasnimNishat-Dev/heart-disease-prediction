# ❤️ Heart Disease Prediction Project

This project aims to predict the likelihood of heart disease in patients based on medical and demographic attributes such as age, sex, blood pressure, cholesterol, and more. The dataset is analyzed, preprocessed, and used to train multiple machine learning models. The goal is to identify patients at risk and compare model performance.

---

## 📂 Dataset

The dataset contains the following variables:

- **Unnamed: 0** – Index  
- **age** – Age of patient  
- **sex** – Gender (1 = male, 0 = female)  
- **cp** – Chest pain type (0-3)  
- **trestbps** – Resting blood pressure (mm Hg)  
- **chol** – Serum cholesterol (mg/dl)  
- **fbs** – Fasting blood sugar > 120 mg/dl (1 = true, 0 = false)  
- **restecg** – Resting ECG results (0-2)  
- **thalach** – Maximum heart rate achieved  
- **exang** – Exercise induced angina (1 = yes, 0 = no)  
- **oldpeak** – ST depression induced by exercise  
- **slope** – Slope of the peak exercise ST segment  
- **ca** – Number of major vessels (0-3) colored by fluoroscopy  
- **thal** – Thalassemia (3 = normal, 6 = fixed defect, 7 = reversible defect)  
- **target** – Presence of heart disease (1 = yes, 0 = no)  

---

## 🛠️ Tools & Libraries

- ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)  
- ![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)  
- ![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)  
- ![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=plotly&logoColor=white)  
- ![Seaborn](https://img.shields.io/badge/Seaborn-9ECAE1?style=for-the-badge&logo=seaborn&logoColor=black)  
- ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white) 

---

## 🛠️ Steps Performed

1. **Data Collection & Exploration**  
   - Loaded CSV dataset and explored using `.info()` and `.describe()`.  
   - Checked missing values, feature distributions, and correlations.

2. **Feature Engineering**   
   - Age Groups (`age_group`) – Patients categorized into age ranges: `<30, 30-40, 40-50, 50-60, 60+`.
   - Cholesterol Level Categories (`chol_level`) – Cholesterol values categorized as Normal, Borderline High, High.
   - High Blood Pressure Flag (`high_bp`) – Binary feature indicating if resting blood pressure exceeds 140 mmHg.
   - Age × Max Heart Rate Interaction (`age_thalach_interaction`) – Captures the combined effect of age and maximum heart rate.
   - Oldpeak Categorization (`oldpeak_cat`) – ST depression levels categorized as None, Mild, Severe.
   - High Cholesterol Flag (`high_chol`) – Binary feature indicating if cholesterol exceeds 240 mg/dl.
   - Sex × Age Interaction (`sex_age`) – Interaction feature capturing age differences by gender.
   - Standardized numeric features for ML models.

3. **Visualization**  
   - Histograms of numeric features (age, cholesterol, blood pressure, etc.)  
   - Correlation heatmap to identify feature relationships  
   - Density plots to compare distributions of heart disease vs non-heart disease patients

4. **Model Training & Evaluation**  
   - Models used:  
     - SVM (Linear Kernel)   

   - Evaluation metrics:  
     - Accuracy (SVM Linear: **86.88%**)  
     - Confusion Matrix  
     - Sensitivity (Recall)  
     - Specificity  

5. **Confusion Matrix Explanation**
   ```python
   print('Patient without Heart Disease Correctly Detected (True Negatives): ', cm[0][0])
   print('Incorrectly Detected as Heart Disease (False Positives): ', cm[0][1])
   print('Heart Disease Patient Missed (False Negatives): ', cm[1][0])
   print('Heart Disease Patient Correctly Detected (True Positives): ', cm[1][1])
   print('Total Heart Disease Patients: ', np.sum(cm[1]))
   print('Sensitivity (Recall): ', cm[1][1] / (cm[1][1] + cm[1][0]))
   print('Specificity: ', cm[0][0] / (cm[0][0] + cm[0][1]))

---
📈 Results
- Best Model: SVM Linear Kernel with 86.88% accuracy
- Feature importance highlighted age, max heart rate (thalach), cholesterol (chol), and ST depression (oldpeak) as strong predictors.
- Engineered features improved model performance and interpretability.

---

🚀 How to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/TasnimNishat-Dev/heart_disease_prediction.git
   cd heart_disease_prediction
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
5. Run the Jupyter Notebook:
   ```bash
   jupyter notebook heart_disease_prediction.ipynb

---
✨ Author

[Sadia Tasnim Nishat]
