# EEG Confusion Detection

This repository contains an analysis of EEG data for detecting confusion in college students watching MOOC video clips. The project includes data preprocessing, exploratory data analysis, and machine learning model training using various classification models, including logistic regression, SVM, KNN, MLP, LSTM, and CNN.

## Repository Contents

### Files

1. **confused_students_agg_mean_by_student.ipynb**:
   - Contains data preprocessing, feature aggregation, and model training for static classifiers:
     - **Logistic Regression**
     - **KNN**
     - **SVM**
     - **MLP (Multi-Layer Perceptron)**
   - Focuses on aggregating EEG data metrics by averaging across `(SubjectID, VideoID)` pairs to capture overall patterns.

2. **confused_students_temporal.ipynb**:
   - Implements sequential models (LSTM and CNN) that leverage the temporal structure of EEG data:
     - **LSTM (Long Short-Term Memory)**: Designed for capturing long-term dependencies in EEG signals.
     - **CNN (Convolutional Neural Network)**: Optimized for identifying localized temporal patterns.
   - Preprocesses EEG data into fixed-length sequences for effective time-series analysis.

3. **EEG_data.csv**:
   - Contains EEG recordings from students as they watched various educational video clips.

4. **demographic_info.csv**:
   - Provides demographic information for each student, including age, ethnicity, and gender.

---

## Project Overview

### 1. **Data Preprocessing**
- For **confused_students_agg_mean_by_student.ipynb**:
  - EEG data is aggregated by averaging metrics (`Attention`, `Delta`, `Theta`, etc.) for each `(SubjectID, VideoID)` pair.
  - Features are normalized, and demographic data is encoded to prepare the dataset for traditional machine learning models.

- For **confused_students_temporal.ipynb**:
  - EEG data is segmented into fixed-length sequences (50 time steps) to retain temporal dependencies.
  - Features are normalized to ensure consistency and compatibility with deep learning models.

### 2. **Model Training**

#### Static Models (Aggregated Data):
- **Logistic Regression**:
  - Baseline classifier with regularization tuning.
- **KNN**:
  - Hyperparameter tuning for the number of neighbors and distance metrics.
- **SVM**:
  - Optimized for classification using kernel tricks.
- **MLP**:
  - Neural network trained on static EEG feature averages, leveraging fully connected layers.

#### Sequential Models (Temporal Data):
- **LSTM**:
  - Captures long-term dependencies in EEG data, achieving a test accuracy of 89.39%.
- **CNN**:
  - Extracts local temporal patterns through convolutional filters, achieving a test accuracy of 95.20%.

### 3. **Evaluation**
- Models are evaluated using accuracy, precision, recall, and F1-score.
- The CNN model demonstrated the best performance, highlighting its effectiveness for time-series EEG analysis.

---

## Key Findings
- **Static Analysis**:
  - Logistic Regression, KNN, SVM, and MLP perform reasonably well on aggregated EEG data, but their ability to capture temporal nuances is limited.
- **Temporal Analysis**:
  - LSTM and CNN models outperform static classifiers by leveraging the temporal structure of EEG data.
  - CNNs excel at identifying local temporal patterns, resulting in state-of-the-art performance.

---

## Future Work
- Investigate the generalizability of the CNN model to other cognitive tasks (e.g., engagement, focus).
- Extend the dataset with additional temporal signals or multi-modal inputs.
- Explore transfer learning for EEG-based emotion or cognitive state classification.
