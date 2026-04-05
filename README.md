# Crop Recommendation System using Machine Learning

This project provides a data-driven approach to agriculture by recommending the most suitable crops to grow based on specific soil and environmental parameters. Using a **Random Forest Classifier**, the system achieves near-perfect accuracy in predicting the best crop for given conditions.

## 🌟 Overview
The goal is to help farmers optimize their yield by analyzing environmental factors. The model considers seven key features:
- **Nutrients:** Nitrogen (N), Phosphorous (P), Potassium (K).
- **Conditions:** Temperature, Humidity, pH value, and Rainfall.

## 🛠️ Technical Stack
- **Algorithms:** Random Forest Classifier (400 estimators).
- **Libraries:** Scikit-learn, Pandas, NumPy, Joblib (for model persistence).
- **Evaluation:** Confusion Matrix and Classification Report.

## 📊 Performance & Results
- **Accuracy:** ~99.3%
- **Classes:** 22 different crops (including Rice, Maize, Chickpea, Kidneybeans, Pigeonpeas, Mothbeans, Mungbean, Blackgram, Lentil, Pomegranate, Banana, Mango, Grapes, Watermelon, Muskmelon, Apple, Orange, Papaya, Coconut, Cotton, Jute, and Coffee).
- **Reliability:** High F1-scores across all categories, indicating a very robust model.

## 🚀 Key Features
- **Top-3 Predictions:** Instead of a single answer, the system provides the top 3 most likely crops with their respective probability percentages.
- **Model Persistence:** The trained model is exported as a `.pkl` file for easy integration into web or mobile applications.

## 📊 Dataset
The model is trained using the **Crop Recommendation Dataset** available on Kaggle. 
- **Source:** [Kaggle - Crop Recommendation Dataset](https://www.kaggle.com/datasets/atharvaingle/crop-recommendation-dataset)
- **Context:** This dataset was build by augmenting various existing datasets (Rainfall, Climate, and Fertilizer) to create a specialized set for precision agriculture.
- **Data Points:** 2,200 instances with 7 features (N, P, K, temperature, humidity, ph, rainfall).

## 💻 Usage
1. **Prepare Data:** Ensure `Crop_recommendation.csv` is in the directory.
2. **Train & Save:** Run the notebook to generate `crop_model.pkl`.
3. **Inference:**
   ```python
   import joblib
   model = joblib.load('crop_model.pkl')
   # Predict for new soil data
   prediction = model.predict([[70, 30, 40, 25, 80, 7, 250]])
