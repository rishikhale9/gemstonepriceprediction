# 💎 Gemstone Price Prediction

A machine learning project to predict the price of diamonds using regression techniques.

---

## 📌 Project Highlights

- 🔍 Predicts diamond prices based on features like carat, cut, color, clarity, dimensions, etc.  
- 📂 Dataset sourced from Kaggle: [Playground Series S3E8](https://www.kaggle.com/competitions/playground-series-s3e8/data?select=train.csv)  
- ⚙️ End-to-end ML pipeline: data preprocessing, model training, prediction, and deployment  
- 🌐 Flask web app for real-time predictions via a user-friendly UI  

---

## 📊 Dataset Details

### Input Features

- `id`: Unique ID  
- `carat`: Weight of the diamond  
- `cut`: Quality of the diamond cut  
- `color`: Diamond color grade  
- `clarity`: Diamond clarity grade  
- `depth`: Height of the diamond (mm)  
- `table`: Width of the top facet (mm)  
- `x`, `y`, `z`: Dimensions of the diamond (mm)  

### Target Variable

- `price`: Diamond price (in USD)  

---

## 🛠️ Approach

### 1. Data Ingestion

- Read raw data from CSV  
- Split into training and test sets  
- Save processed data locally  

### 2. Data Transformation

- Create a preprocessing pipeline:
  - **Numerical columns**: `SimpleImputer(median)` + `StandardScaler`
  - **Categorical columns**: `SimpleImputer(most_frequent)` + `OrdinalEncoder` + `StandardScaler`
- Save pipeline as `preprocessor.pkl`

### 3. Model Training

- Test baseline models  
- Train using `CatBoostRegressor`  
- Tune `CatBoost` and `KNN`  
- Build final `VotingRegressor` using:
  - `CatBoost`
  - `XGBoost`
  - `KNN`  
- Save model as `model.pkl`

### 4. Prediction Pipeline

- Load preprocessor and model files  
- Convert user input to DataFrame  
- Make predictions on new data  

### 5. Flask Web App

- Create a web interface for input and prediction  
- Deployable locally or on cloud platforms  

---

## ✅ Acknowledgement

> This project is a student initiative by **Rishi Khale**.  
> A great example of knowledge sharing — kudos for making it public!
