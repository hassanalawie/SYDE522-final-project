# EEG Confusion Detection

This repository contains an analysis of EEG data for detecting confusion in college students watching MOOC video clips. The project includes data preprocessing, exploratory data analysis, and machine learning model training using SVM and KNN classifiers.

## Repository Contents

- **EEG_data.csv**: Contains EEG recordings from students as they watched various educational video clips.
- **demographic_info.csv**: Provides demographic information for each student, including age, ethnicity, and gender.
- **EEG_Confusion_Detection.ipynb**: Jupyter Notebook that walks through data preprocessing, model training, and evaluation.

## Project Overview

1. **Data Preprocessing**: The EEG data is aggregated by averaging metrics like `Attention`, `Mediation`, `Delta`, `Theta`, etc., for each `(SubjectID, VideoID)` pair to capture overall brain activity patterns. Demographic features are encoded, and numerical features are standardized to prepare the data for machine learning.

2. **Model Training**: 
   - **SVM** and **KNN** classifiers are trained on the preprocessed data.
   - Hyperparameter tuning is performed to optimize model performance.

3. **Evaluation**: Models are evaluated based on accuracy, precision, recall, and F1-score, with optimal parameters identified for each model.