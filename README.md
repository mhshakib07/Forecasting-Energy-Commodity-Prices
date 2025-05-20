# Forecasting Energy Commodity Prices with Deep Neural Networks  

A deep learning project predicting crude oil and natural gas prices using **LSTM, CNN, and hybrid models (LSTM + CNN)** to address volatility in energy markets. Achieves **R² > 0.9** with uncertainty-aware future projections.

---

## 📌 Problem Statement  
Energy commodity prices (e.g., crude oil, natural gas) are highly volatile, impacting global economies. This project:  
- Develops **time-series forecasting models** to predict daily settlement prices.  
- Compares performance of **LSTM, CNN, and hybrid architectures**.  
- Provides actionable insights for traders, policymakers, and energy analysts.  

## 🛠️ Methodology  

### **Dataset**  
- **Source**: https://www.kaggle.com/datasets/albertobircoci/historical-prices-of-major-natural-resource/data
- **Time Range**: Daily prices (January 1997 – March 2023)  
- **Features**:  
  - `Settle`: Daily closing price (target variable).  
  - Derived features: Moving averages (14-day), volatility indicators.  

### **Models Implemented**  
| Model          | Architecture                          | Key Hyperparameters              |  
|----------------|---------------------------------------|----------------------------------|  
| **LSTM**       | 2 LSTM layers (64 units each)         | Dropout=0.2, Seq length=30 days |  
| **CNN**        | 1D Conv + MaxPooling                  | Kernel size=3, Filters=64       |  
| **Hybrid**     | CNN (feature extraction) + LSTM       | Combined best of both approaches |  

### **Metrics**  
- **RMSE**, **MAE**, **R² Score** (tested on 20% holdout data).  

---

## 📊 Results  

### **Crude Oil Forecasting**  
| Model       | RMSE  | MAE   | R² Score |  
|------------|-------|-------|----------|  
| LSTM       | 5.37  | 3.95  | 0.9053   |  
| CNN        | 5.70  | 4.45  | 0.8935   |  
| **Hybrid** | **4.80** | **3.58** | **0.9246** |  

### **Natural Gas Forecasting**  
| Model       | RMSE  | MAE   | R² Score |  
|------------|-------|-------|----------|  
| LSTM       | 0.55  | 0.36  | 0.9094   |  
| CNN        | 0.58  | 0.39  | 0.9005   |  
| **Hybrid** | **0.53** | **0.35** | **0.9161** |  

**Key Insight**: Hybrid (CNN+LSTM) outperforms standalone models by **2-3% in R²**.  
