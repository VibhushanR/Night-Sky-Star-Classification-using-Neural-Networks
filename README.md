# 🌌 Night Sky Star Classification Using Neural Networks

## 📌 Business Problem
Astronomers often struggle to accurately classify celestial objects—particularly quasars—due to feature overlap and class imbalance in telescope data. Manual classification is time-consuming and error-prone. This project leverages neural networks to automate the classification of stars, galaxies, and quasars, aiming to:
- Improve quasar identification accuracy
- Reduce manual labeling efforts
- Support cosmological research through better data-driven workflows

## 🧾 Dataset Overview
The dataset includes positional, photometric, and spectral attributes of celestial objects:
- **Classes:** GALAXY, STAR, QSO (quasar)
- **Features:** Redshift, alpha, delta, photometric filters (u, g, r, i, z), object ID
- **Challenge:** Class imbalance (GALAXY dominates)

## 🔍 Exploratory Data Analysis Highlights
- **QSOs** have the **highest redshift values**, confirming they are farther in space.
- **Class imbalance**: GALAXY > STAR > QSO → calls for resampling.
- **Observation dates** are uniform, but QSO sightings cluster during specific survey periods.

## 🧪 Data Balancing: SMOTE + Undersampling
- Applied **SMOTE** to synthetically balance underrepresented QSO and STAR classes.
- **Undersampled** GALAXY to prevent model bias.
- Resulted in significantly improved classification metrics across all classes.

## 🧠 Neural Network Architectures Tested
1. **NN 10** – Shallow, 1 hidden layer (10 neurons)
2. **NN 2-4-2** – Deep and narrow (3 hidden layers: 2, 4, 2 neurons)
3. **NN Deep 50** – Wide network, 1 hidden layer with 50 neurons (best performance)

## 📈 Model Evaluation
- **Best model**: `NN Deep 50`  
  - Accuracy: **97.7%**
  - F1-score: **0.977**
  - AUC: **0.997**
- **Confusion matrices**: Show significant improvement in QSO detection post-SMOTE
- **ROC Curves**: NN Deep 50 curve closely hugs the top-left corner → excellent classification

## 🔬 Feature Importance & Explainability
- **Top feature:** `Redshift` (most critical for identifying quasars)
- **Key photometric bands:** u, g, i, r
- **Low-impact features:** Positional (alpha, delta)

## 📌 Recommendations
- ✅ **Deploy NN Deep-50** for production
- 🔁 **Use SMOTE** for consistent preprocessing in future models
- 🎯 Focus on **redshift and photometric filters** for feature engineering
- 🧪 Investigate **QSO-Star misclassification** further using advanced modeling (e.g., ensemble methods)

## 🛠 Tools Used
- **Orange Data Mining** – Model building and workflows
- **Python (optional)** – For additional analysis or data preparation
- **SHAP** – For feature importance visualization

