# digits-pca-exploration
# 🖼️ Digits PCA Exploration

**An interactive deep-dive into Principal Component Analysis on the scikit-learn Digits dataset.**

---

## 📖 Project Overview

This notebook demonstrates how to use PCA to:

- Compress 64-dimensional handwritten-digit data down to a handful of components  
- Visualize high-dimensional data in 2D  
- Quantify and plot explained variance per component  
- (Optionally) feed PCA outputs into a classifier and measure performance  

It’s a purely educational exercise—no business use-case—meant to showcase fundamentals of dimensionality reduction.

---

## 📂 Dataset

- **Source:** `sklearn.datasets.load_digits()`  
- **Samples:** 1,797 handwritten digit images (8×8 pixels, flattened to 64 features)  
- **Labels:** Digit classes 0–9  


## Gym Dataset Regression with PCA

- **Dataset:** `GYM.csv` 
- **Cleaning:** Dropped duplicates; imputed missing values with column means  
- **Models:**
  1. **Baseline:** `StandardScaler` → `LinearRegression` ⇒ RMSE = *rmse_1*  
  2. **PCA‐Enhanced:** `StandardScaler` → `PCA(n_components=0.95)` → `LinearRegression` ⇒ RMSE = *rmse_2*  
- **Comparison:** Prints whether PCA preprocessing improved (lowered) RMSE.


---

## 🔧 What’s Inside

1. **Data loading & sanity checks** (missing values, duplicates)  
2. **Standard scaling** to zero-mean/unit-variance  
3. **PCA experiments**:  
   - `n_components=0.95` (retain 95% variance)  
   - `n_components=2` (for 2D visualization & reconstruction)  
4. **Classifier demo**: Logistic Regression on PCA features  
5. **Visualization**:  
   - Cumulative explained variance plot  
   - 2D scatter of first two PCs  
6. **Reconstruction & loss**: measure variance lost when projecting back from 2D  

--

Since the PCA‐enhanced model achieved a lower RMSE, applying PCA helped by removing redundant information and reducing overfitting on the Gym data.
