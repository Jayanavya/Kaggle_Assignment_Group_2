# Kaggle_Assignment_Group_2
# Project Title - SPACESHIP TITANIC

**Files in This Project**
Kaggle_Code.ipynb – Main code notebook that contains everything from data cleaning to model training

train.csv – The dataset used to train the machine learning models

test.csv – Unlabeled data used to make final predictions

submission.csv – The final predictions file to upload to Kaggle

# Steps in the Project
**1. Importing Libraries**
We use tools like Pandas, NumPy, Scikit-learn, XGBoost, and TensorFlow to help us work with data and build models.

**2. Loading the Data**
We load the training and test datasets and take a first look at the columns, missing values, and general structure.

**3. Cleaning the Data**
Handled about 24% missing values using smart methods:

Used the most common value (mode) for text-based columns

Used the middle value (median) for number columns

**4. Feature Engineering**
We created new useful columns from existing ones:

Broke the Cabin column into Deck, Cabin_num, and Side

Cleaned spending columns and filled missing values smartly based on CryoSleep status

**5. Encoding Categorical Data**
Since machine learning models can't read text directly, we converted text columns to numbers using Label Encoding.

**6.  Models Used and Hyperparameters**
# Logistic Regression

Tuned using GridSearchCV over:

solver: liblinear, saga

penalty: l1, l2

C: [0.01, 0.1, 1, 10, 100]

Purpose: baseline model and regularization testing (L1 for feature selection, L2 for smoothing).

Best model chosen based on cross-validation accuracy.

# XGBoost

Used with:

eval_metric='logloss'

random_state=42

Quick and effective on structured/tabular data.

Handled missing values and complex patterns without deep tuning.

Achieved accuracy of ~0.7999.

# LightGBM

Initialized with:

random_state=42

Fast training and efficient memory use.

Achieved the best Kaggle score: 0.80702, outperforming XGBoost
**7. Evaluated models using:**
accuracy_score

ConfusionMatrixDisplay

Other metrics like precision, recall, and F1-score

**8. Explaining the Predictions**
SHAP (SHapley Additive exPlanations) is a tool used in the field of Explainable AI (XAI).
We used SHAP values to understand which features were most important in making predictions.

**9. Making Final Predictions**
Used the best model (Light BGM) to predict on the test dataset and created a submission.csv file to upload to Kaggle.

